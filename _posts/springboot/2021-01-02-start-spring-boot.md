---
title: "[스프링부트로 Rest API 만들어보기] 스프링부트 프로젝트 시작하기"
excerpt: "start.spring.io"
toc: true
toc_sticky: true
categories:
    - server
tags:
    - server
last_modified_at: 2021-01-02T14:20:00-09:00
---
## 스프링 부트 프로젝트 시작하기
프로젝트를 시작할때 [start.spring.io](https://spring.io/quickstart) 를 이용하면 간편하게 초기 세팅을 마칠 수 있다.
사이트에 접속을 하면 아래와 같은 화면을 볼 수 있다.   
![메인 페이지](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/springboot/images/start1.PNG)  
화면에 보이는대로 원하는 환경을 세팅하도록 한다. 본 시리즈에서는 gradle을 사용하여 의존성 관리를 할거기 때문에 gradle을 선택했다.  
![의존성 선택](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/springboot/images/start2.PNG)  
우측의 Dependencies 옆의 ADD를 누르면 위와같은 화면이 나온다. 여기서는 이 프로젝트에 추가할 외부 의존성을 선택하면 된다.  
![선택한 의존성](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/springboot/images/start3.PNG)    
이번 시리즈에서 사용할 의존성들을 선택한 모습이다.   
![미리보기](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/springboot/images/start4.PNG)  
이제 설정한 것들을 전부 추가했으면 바로 generate를 누르면 다운로드가 되는데 그전에 explore를 눌러 원하는대로 세팅되었는지 확인해준다.  

## 실행해보기
이제 다운받은 프로젝트를 실행해 보자.  Springboot를 사용하여 프로그래밍을 할때는 Intellij를 추천한다.  
초기에 프로젝트를 IDE에서 실행을 하면 gradle이 앞에서 설정한 외부 의존성을 체크해서 세팅을 해주는것을 기다린 후 실행을 해본다.  
![실행해 보기](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/springboot/images/start5.PNG)  
위와 같은 모습이 콘솔에 보이면 성공적으로 실행되고 있는것이다.

## 마무리
지금까지 스프링부트 프로젝트 초기설정을 해 보았다. 다음 포스트에서는 사용자의 요청을 받는 컨트롤러를 만들어보자.


