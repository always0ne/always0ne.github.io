---
title: "시각장애인을 위한 버스 시스템 개선 프로젝트"
excerpt: "시각장애인도 편하게 버스를 탑승할수 있는 시스템을 만들어보자"
categories:
    - projects
tags:
    - project
    - SpringBoot
    - Android
    - openData
    - voice
last_modified_at: 2020-06-12T13:30:00-09:00
---
## 내가 한 일
- 팀장
- 시스템 기획/ 설계
- API 서버 개발
- 음성인식 모듈 개발
- 안드로이드 통신모듈 개발

## 제공되는 기능
- 주요사용자가 시각장애인이기 때문에 음성인식 시스템이 제공된다.
- 현재 위치가 정류장인지, 어느 정류장인지 확인하는 기능
- 승차할 버스를 예약하고, 이전정류장 출발 시 앱 알림, 도착 시 버스입구에서 버스번호 알림 기능
- 하차할 정류장을 지정하고, 이전 정류장 출발 시 앱알림, 자동 하차벨 작동 기능

## 사용된 기술 및 장비
- Java
- Android
- Komoran(한국어 형태소 분석기)
- OpenData
- TTS/STT

## 프로젝트 소개
3학년 1학기 소프트웨어프로젝트 과목의 프로젝트를 기획하던 중 시각장애인이 버스를 이용하는데 많은 불편을 느끼고 있으며 
시스템의 개선이 필요하다는 뉴스와 국민청원을 보고 시작한 프로젝트이다.

###### 버스 이용시 시각장애인들은 아래와 같은 불편을 겪는다고 한다.
- 버스 정류장 식별(노선에 맞는 정류장 위치)
- 버스 식별(원하는 노선의 버스의 위치/도착여부)
- 하차 벨 식별

우리는 위 문제들을 시각장애인과 버스업체가 최소한의 추가장비로 해결할수 있도록 해결하고자 하였다.
그래서 우리는 공공데이터 포탈에서 제공하는 데이터를 활용하는 스마트폰 앱의 형태로 기획을 하였다.

위 기능들을 버스의 교통카드 단말의 기능추가를 하는 방법으로 설계를 하였고, 실제로 단말을 임시로 구현해 실시간으로 기능이 동작하는지 확인해 보았다.
 
 현재 전맹이 아닌 시각장애인을 위해 버튼UI적용도 검토중이다.

- [프로젝트 살펴보러 가기](https://github.com/Cobitsa)  
