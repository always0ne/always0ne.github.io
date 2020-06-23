---
title: "SpringBoot RestAPI Templet"
excerpt: "스프링 부트로 RestAPI를 지원하는 템플릿을 만들어보자"
categories:
    - projects
tags:
    - project
    - SpringBoot
    - RestAPI
last_modified_at: 2020-06-23T13:30:00-09:00
---
SpringBoot로 토이 프로젝트를 여러개 돌리며, 같은 코드에 서비스 로직만 바뀌는 듯한 느낌이 들어
 퀵스타트용 템플릿을 만들어두면 나중에 유용할 것 같아서 시작한 프로젝트이다.

RestFul Api 스펙을 전부 만족할 수 있도록 설계하였다.  
대표적으로 RestFul Api에서 잘 지켜지지 않고 있는 Self-descriptiveness을 지원하기 위해 HAL을 적용해 (HATEOAS)를 사용한다.
 
간단한 CRUD 예제, 연관매핑, APIDocs, Docker에 대한 세팅이 포함되어있으며, 앞으로 SpringBoot로 RestApi를 구현하는데
필수라 생각되는 기능들을 추가해 나가며, 최적화 해 나갈 예정이다. 

[프로젝트 살펴보러 가기](https://github.com/always0ne/SpringBootRestApiTemplet)  
