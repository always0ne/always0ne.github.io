---
title: "서버는 무엇일까?"
excerpt: "간단한 서버 지식"
toc: true
toc_sticky: true
categories:
    - server
tags:
    - server
last_modified_at: 2020-10-12T22:20:00-09:00
---
## 서버는 무엇인가
클라이언트에게 네트워크를 통해 정보나 서비스를 제공하는 컴퓨터 시스템으로 컴퓨터 프로그램(**server** program) 또는 장치(device)를 의미한다. 시장에 있는 음식점에서 밥을 먹는걸로 비유를 해보자
```
손님(Client)은 밥을 먹으러  시장(Network)에 갔다. 
그리고 음식점(Domain)을 들어가서 직원(Server)에게
식사(Service/Data)를 주문해 먹었다.
```
Network는 Client와 Server들이 모인 곳이고, Client가 Server에게 서비스 혹은 정보를 요청하여 제공받는 것이 일반적이다. 중요한건 이는 역할로 나누어진것이기 때문에 어느 형태의 컴퓨터든 네트워크를 통해 서비스를 제공하면 서버라고 할 수 있다(예를들면 프리메이플서버). 다만 24시간동안 다수의 사용자를 받기 위해 최적화된 장비를 많이 사용한다.
## 서버의 종류
### 웹 서버
HTTP(Hyper Text Transfer Protocol)프로토콜을 사용하여 클라이언트와 정적인 통신을 하는 서버이다. 우리가 웹브라우저를 켰을때 나오는 컨텐츠들을 제공하는것이 제일 대표적인 활용예이다.
웹페이지의 기본인 HTML(HyperText Markup Language)을 제공하기 위해 개발되었고, 이쁘고, 기능을 넣기 위해 CSS, JavaScript, Image/video 컨텐츠들도 전달되고 있다.
대표적인 예로는 Apache, Nginx 등이 있다.

###  웹 어플리케이션 서버
흔히 말하는 백엔드가 주로 이부분이다. 정적인 웹 페이지를 동적으로 사용하기 위해 만들어진 서버이다. 사용자가 요청한 것에 맞게 DB와 연동해 페이지를 제작(렌더링)해서 클라이언트에 전달한다. 
대표적인 예로JSP +  톰캣, PHP등이 있다.

### 데이터베이스 서버
서버 역할을 하다보면 정말 많은 데이터를 수집하고, 정리하며 제공하게 된다. 이를 전부 파일로 관리하면 유지보수도 어려울뿐더러 성능문제가 발생하게 된다. 그렇기 때문에 데이터만 중점으로 관리해주는 서버가 생겻다. 대표적인 예로 MySQL, ORACLE, Maria 등이 있다.

### 파일 서버
우리가 흔히 생각하는 클라우드 서버이다. 파일을 대신 저장해주고 다운로드 서비스를 제공하는 서버이다.

###  메일 서버
SMTP(Simple Mail Transfer Protocol)를 이용해 메일 전송을 해주는 서버이다.  gmail , 네이버 메일 등은 이 서버를 사용하여 서비스를 제공한다.

### 게임 서버
개인적으로 서버 개발의 꽃이라고 할수 있다고 생각한다.
실시간으로 고품질의 게임 서비스를 제공하며 데이터 유실도 없어야 한다. 성능에 매우 신경을 써 직접 Low Level 단계의 많은 것을 개발하는 편이다.  성능과 안정성에 클라이언트가 매우 예민해 게임회사에 서버 개발자로 가면 집을 구할 필요가 없다는 말이 있다.

###  프록시 서버
프록시 서버는 클라이언트가 자신을 통해서 다른 네트워크 서비스에 간접적으로 접속할 수 있게 해주는 서버이다. 중계기라고 생각하면 편하다.
보통 보안망에 접속하거나, 본인의 IP를 숨기고 인터넷을 사용하거나, 네트워크 성능을 위해 캐싱을 할때 사용된다.

### 컴퓨팅 서버
일종의 슈퍼 컴퓨터로, 다양한 분야에서 사용되는 초고속/대용량 컴퓨터를 의미한다. 특수하게 자원을 많이 먹는 경우(머신러닝) 의뢰해서 사용하는 형식이다.