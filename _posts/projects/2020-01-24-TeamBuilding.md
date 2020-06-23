---
title: "대학생 공모전 팀빌딩 플랫폼"
excerpt: "개발, 기획, 디자인 등 여러 전문분야를 가진 대학생들을 연결해주자"
categories:
    - projects
tags:
    - project
    - SpringBoot
    - RestAPI
last_modified_at: 2020-06-23T13:30:00-09:00
---
대학 후배가 방학동안 같이 프로젝트를 하자 해서 시작한 프로젝트이다.  
항상 공모전 나갈 팀원 찾는데 어려움이 있던 기억이 있어 내가 기획을 하고, 서버를 당담중인 프로젝트이다.  

앱 버전 개발도 고려중이여서 React, SpringBoot를 사용한 SPA기반의 RestApi를 사용하는 웹서비스를 개발중이다.  
HAL을 적용해 (Hateoas)를 사용하면서 클라이언트가 각 페이지의 인덱스를 제외한 URL을 보유하지 않음으로써
URL 의존성을 해소 하고, 권한별로 제공되는 인터페이스만 동작할 수 있도록 설계하였다. 

CI/CD 자동화도 적용해 도커로 서버에 배포도 해 보았다.   
초기에 Jenkins 서버를 구축해서 CI/CD를 하다 Github Actions를 발견하고, 적용해 보는 중이며 만족스럽게 사용하는 중이다.

Git Flow 워크 플로우 도입, 슬랙 봇 사용, 노션 사용등 여러 협업 방식을 적용해 보고 있는 중이다.  

[프로젝트 살펴보러 가기](https://github.com/always0ne) (현재 비공개로 개발중이여서 추후 공개 예정) 