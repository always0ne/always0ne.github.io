---
title: "IoT 빨래 건조대"
excerpt: "생활안전을 위한 세탁물 IoT모니터링 시스템"
categories:
    - projects
tags:
    - IoT
    - project
    - 특허
    - 논문
last_modified_at: 2020-06-17T13:30:00-09:00
---
## 내가 한 일
- 시스템 설계
- 기상청 RSS 실시간 파싱
- 네트워크 환경 구축
- GUI

## 제공되는 기능
- 빨래 건조 완료 시각 예측
- 건조중이거나 건조시작할 떄 예측시간안에 비가 예상되면 알림

## 사용된 기술 및 장비
- C
- GTK
- Ardoino
- Rasberry Pi

## 프로젝트 소개
 2016년에 대학에 입학하고 1학년때 창의적 공학 설계 과목에서 처음으로 직접 설계한 프로젝트이다.  
 
빨래를 실외에서 건조할 때, 빨래가 언제 마르는지 예측해주고, 비가 올것으로 예상되었을 때 알림을 제공하는 간단한 프로젝트였다.
지금 소스를 다시 들여다 보면 고칠점이 상당히 많지만 그 당시에는 처음으로 GUI도 짜보고 네트워크도 만져봐서 상당히 재밌게 했던 기억이 있다.  

빨래 건조대에 아두이노를 장착하고, 센서들과 와이파이 모듈을 달아 측정된 데이터를 내부 와이파이망에서 
Web API로 공유를 하면, 실내에 있는 관리자 단말이 주기적으로 파싱한 기상청 데이터와 함께 분석을 하여 
빨래의 건조시간을 예측하고, 비가 올 예정일시 알림을 제공해 빨래를 들여놓을 수 있게 하였다.

과목 1위를 차지하면서 상도 받고, 학술대회 논문과 특허를 학교를 통해서 낼 수 있는 기회를 얻어,
2017 한국정보처리학회에서 은상을 탓고,  2018년 8월부로 특허가 등록되었다.
 
- [논문정보](https://www.koreascience.or.kr/article/CFKO201725864428249.page)  
- [특허정보](http://www.ndsl.kr/ndsl/search/detail/patent/patentSearchResultDetail.do?cn=KOR1020170049076)