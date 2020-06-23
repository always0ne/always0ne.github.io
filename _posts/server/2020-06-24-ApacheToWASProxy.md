---
title: "Proxy Pass를 사용하여 Apache Web Server에 WAS 연동하기"
excerpt: "Reverse Proxy를 사용하여 웹 서버(apache)에 웹 어플리케이션 서버(was)를 연동해 보자"
toc: true
toc_sticky: true
categories:
    - server
tags:
    - server
    - proxy
    - apache
last_modified_at: 2020-06-24T02:20:00-09:00
---
## 무엇을 할 것인가
- 본 게시글은 아파치를 사용하여 한 서버에 여러 서비스를 호스팅 하고 싶을때
 [리버스 프록시](/server/Proxy/#2리버스-프록시reverse-proxy)를 사용해 구현하는 법을 서술할 것이다.
 - apache를 WAS랑 연동할때 이 방법을 사용하여도 좋다.(오히려 간단해서 좋다)
 - 본 게시글에서는 HTTPS를 지원하는 것을 전제로 한다.
 
 ## 직접 해보기
 리버스 프록시를 사용하여 웹 어플리케이션을 연동을 하기 위해선  apache conf파일에 아래와같이 VirtualHost를 추가해 주면 된다.

```
<VirtualHost *:443>

  ServerName domain.com
  ServerAlias <원하는 주소> ex)blog.domain.com or www.domain.com...
  ServerAdmin <email주소>

  ProxyRequests Off
  SSLProxyEngine on
  ProxyPreserveHost On
  AllowEncodedSlashes NoDecode

  <Proxy *>
    Order deny,allow
    Allow from all
  </proxy>

  SSLEngine on
  SSLProxyVerify none
  SSLProxyCheckPeerCN off
  SSLProxyCheckPeerName off
  SSLProxyCheckPeerExpire off
  SSLCertificateFile "<인증서 경로>/cert.pem"
  SSLCertificateKeyFile "<인증서 경로>/privkey.pem"
  SSLCertificateChainFile "<인증서 경로>/chain.pem"

  ProxyPass / http://127.0.0.1:8080/
  ProxyPassReverse / http://127.0.0.1:8080/

  RequestHeader set X-Forwarded-Proto "https"
  RequestHeader set X-Forwarded-Port "443"

  ErrorLog <로그 경로>/docker-error.log
  CustomLog <로그 경로>/docker-access.log combined

</VirtualHost>
```
### VirtualHost
web Server는 Main Host외의 별도의 가상 Host를 사용하여 1개의 서버에서 여러개의 웹서버를 운영할 수 있다.
본 게시글에서는 WAS를 연동하는 것이 목적이기 때문에 DocumentRoot를 사용하는 대신 RerverseProxy를 사용할 것이다.  

#### 도메인 세팅
`ServerName`은 서비스할 도메인이며 `ServerAlias`는 서버의 별칭이다.

#### 로그 세팅
`ErrorLog`는 에러로그의 경로이며, `CustomLog`는 접속 로그의 경로이다.

#### 프록시 세팅
- `proxyRequests Off`  
 on일 경우 Forward Proxy로 동작, off일 경우 Reverse Proxy로 동작하는 옵션이다.
- `proxyPreserveHost On`  
 HTTP 요청 헤더의 Host: 부분을 유지하는 옵션이다.
- `AllowEncodedSlaxhes NoDecode`  
 웹 서버 뒤에서 인코딩된 /를 디코딩 하지 않도록 설정하는 옵션이다.
- `<proxy *> Order deny,allow  Allow from all </proxy>`  
프록시에 대한 보안 설정이다.  
deny조건을 먼저 확인한 후  allow조건을 확인하며, 모든 호스트에서 접속이 가능하다.
- `proxypass /<이곳에 경로를 설정해도 된다 ex)blog> http://127.0.0.1:8080/`  
위 세팅을 기준으로 설명했을 때, 외부에서 들어온 www.domin.com/blog/posts/1 요청을
 127.0.0.1:8080/posts/1로 변환시켜주는 기능이다
- `proxypassReverse /<이곳에 경로를 설정해도 된다 ex)blog> http://127.0.0.1:8080/`  
위의것과 기능은 동일하지만, 내부에서 리다이렉트가 일어났을시 생성되는 URL의 도메인이 127.0.0.1:8080/이
 되버리기 때문에 이를 다시 www.domain.com/으로 변환해주는 기능이다.

##### SSL을 위한 Proxy Settings
- `RequestHeader set X-Forwarded-Proto "https"`  
- `RequestHeader set X-Forwarded-Port "443"`  
프록시를 타고 들어온 요청이 Https요청이고, 443번 포트를 통해 왔음을 알리는 헤더를 추가하는 기능이다.
- `SSLProxyEngine on`  
- `SSLProxyVerify none`  
- `SSLProxyCheckPeerName off`  
- `SSLProxyCheckPeerExpire off`  
프록시 서버에서 SSL검증을 하였기 때문에 중계된 서버에서 검사를 할 필요가 없음을 알리는 세팅이다.

### SSL 세팅
- `SSLEngine on`
- `SSLCertificateFile "<인증서 경로>/cert.pem"`
- `SSLCertificateKeyFile "<인증서 경로>/privkey.pem"`
- `SSLCertificateChainFile "<인증서 경로>/chain.pem"`

SSLEngine을 사용하여 Apache가 SSL을 지원하도록 하는 옵션들이다. 
이때, `<VirtualHost *:443>`로 443포트로 매핑해주는 것이 좋다.

## 마무리
virtual host와 reverse Proxy를 사용하여 WAS를 apache WebServer와 연동을 하였다.  
응용으로 virtualHost를 여러개 생성해 적용을 하면 한 서버에 여러 도메인을 올려 사용할 수 있기도 하며,
 한 프록시 서버로 내부망의 모든 서버의 접근을 관리할 수 있다.
