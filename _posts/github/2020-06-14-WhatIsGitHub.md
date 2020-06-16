---
title: "GitHub 이 뭐죠?"
excerpt: "GitHub은 무엇이며 언제쓰는건가"
toc: true
toc_sticky: true
categories:
    - GitHub
tags:
    - GitHub
last_modified_at: 2020-06-15T12:02:00-09:00
---
## GitHub가 뭐죠?
GitHub는 대표적인 개발 협업 툴인 Git을 무료로 호스팅해주는 서비스이다.  
공개 프로젝트만 무료였지만, 최근에 MS(마이크로소프트)에 인수되어
 비공개저장소도 무료화가 되었고 최근 프로젝트 운영에 도움이 되는 요소가 많이 추가되었다.  

## 그럼 Git은 뭔데요?
Git은 소스코드를 효과적으로 관리하기 위해 개발된 분산형 버전관리 시스템이다.  
```
Git is a free and open source distributed version control system
designed to handle everything from small to very large projects
with speed and efficiency.
```
Git 공식 페이지에서 설명하는 Git이다. 설명에 나오는대로 굉장히 빠르고 강력하다.  
![처참한버전관리](/_posts/github/images/WhatIsGit1.JPG)  
문서나 프로그램을 작성할 때 위와같이 파일을 저장하다 어느 파일이 최신인지 헷갈리거나, 실수로 작성한 내용을 날린 경험이 한두번쯤은 있을 것이다.  
이럴 때 Git을 사용하면 아래와 같이 여러 복사본을 만들지 않고도 버전별로 파일을 관리할 수 있다.  
![Git을 사용하였을 때](/_posts/github/images/WhatIsGit2.JPG)  
또한 아래와 같이 어느부분이 변경되었는지 확인이 가능해 빠르게 분석이 가능하다.    
![diff를 사용했을 때](/_posts/github/images/WhatIsGit3.JPG)  
위의 두가지 기능만 있어도 Git을 사용해야 하는 이유는 충분하다고 개인적으로 생각한다.  

## Git의 역사
Git은 Linux를 만든 리누스 토발즈가 2005년에 Linux개발을 관리하기 위해 개발되었다.  
Git이 만들어진 이유는 생각보다 단순한데 Linux의 버전관리를 할때 사용하던 BitKeeper를 사용하고 있었는데 
Linux커뮤니티의 한 개발자가 BitKeeper의 통신프로토콜을 리버싱하여 해킹을 한 의혹이 제기된 이후로
 공짜로 사용할 수 없게 되어 리누스 토발즈가 뚝딱 하고 만들어버렷다.  
이후 Linux를 대표로 오픈소스 커뮤니티와 함께 지속적으로 성장해 나가며, 
전세계에서 성능과 안정성을 모두 검증받은 최고의 분산버전관리 시스템이며,
 GitHub, BitBucket, GitLab등의 여러 Git 원격 호스팅 플랫폼이 생겨났다.  
 
## 그래서 GitHub는
Git 저장소를 온라인으로 호스팅을 하여 여러명이서 협업을 할 수 있도록 호스팅 해주는 플랫폼이다.  
과거에는 공개 프로젝트만 무료로 제공을 하여 오픈소스 소프트웨어의 성지가 되어갔고,
 구경을 하다보면 양질의 오픈소스를 많이 발견할 수 있으며, 라이센스만 잘 만족하면 자유롭게 사용할 수 있다.  
최근 MS가 인수를 함으로써 Private 저장소 무료화, 여러가지 유용한 유틸리티 제공등의 개선이 일어나고 있어
개인적으로 원격 Git 호스팅 서비스 중에 제일 사용하기 편하다고 생각한다.

 