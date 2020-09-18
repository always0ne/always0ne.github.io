---
title: "Portainer로 편하게 Docker 관리하기"
excerpt: "GUI로 Docker를 편하게 관리해 보자"
toc: true
toc_sticky: true
categories:
    - server
tags:
    - server
    - Docker
    - Portainer
last_modified_at: 2020-09-19T00:20:00-09:00
---
## Portainer는 Container관리를 쉽게하기 위한 툴이다.
서버를 자주 만지고 자동화를 하다보면 도커를 많이 만지게 된다.
커멘드로 사용해도 충분히 잘 활용할 수 있지만 GUI로 관리해주는 Portainer라는 서비스를 사용하면 훨씬 더 편하게 도커를 관리할 수 있다.

## Portainer 사용해 보기
### 설치하기

```
sudo docker run \
-d -p 9000:9000 \
--name=portainer \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
--restart=always \
portainer/portainer
```

도커를 설치한 후 위 명령만 내리면 Portainer를 사용할 수 있다.
### 세팅하기
`http://Ip address:9000`으로 접속 하면 아래 같은 화면을 볼 수 있다.  
![Portainer 계정 만들기](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer1.JPG)  
본인이 사용할 계정을 만들면 된다.  
![Docker 환경 세팅하기](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer2.JPG)  
본인의 환경에 맞는 버튼을 클릭하면 된다.  
![로그인 후 화면](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer3.JPG)  
세팅이 끝나고, 로그인을 하면 이와 같은 화면을 볼 수 있다. 간단한 현황을 볼 수 있다.  
![대시보드](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer4.JPG)  
엔드포인트를 선택하면 상세 정보를 볼 수 있다.  
### App 템플릿
![App 템플릿](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer5.JPG)  
Portainer는 많이 쓰이는 도커 이미지에 대해 템플릿을 제공한다.   
![App 템플릿 사용](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer6.JPG)  
템플릿을 선택하면 위와같이 기본적인것들은 다 세팅되어있고, 비어있는 부분만 채워도 컨테이너 구동이 가능하다    
### 컨테이너
![컨테이너 리스트](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer7.JPG)  
컨테이너 리스트를 선택하면 현재 엔드포인트의 도커 현황을 볼 수 있다. `running`, `healthy`, `unhealthy`, `stopped`상태가 존재한다.  
![컨테이너 내부 접근](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer8.JPG)  
`Quick actions`의 제일 오른쪽 쉘처럼 생긴 버튼을 누르면 컨테이너 내부로 접근이 가능하다.  
![도커 컨테이너 생성](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/server/images/Portainer9.JPG)  
`add container`를 누르면 도커 이미지를 간단하게 실행시킬 수 있다.
## 마무리
도커를 Gui로 관리할 수 있는 Portainer를 사용해 보았다.  
개인적으로 도커를 관리하면서 유용하게 사용하고 있다.  
도커가 어렵다고 생각이 들면 이 서비스를 사용해서 입문해 보는것도 좋을 것 같다.  
[Portainer 공식 페이지](https://www.portainer.io/)
