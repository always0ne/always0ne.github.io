---
title: "gitignore로 레포지터리를 깔끔하게 관리하기"
excerpt: "gitignore로 커밋에 제외할 파일들을 지정해주자"
toc: true
toc_sticky: true
categories:
    - github
tags:
    - github
last_modified_at: 2020-06-26T00:30:00-09:00
---
프로젝트를 진행하다보면, 개인적인 컴퓨터, IDE의 세팅, 개인적인 테스트 파일들을 만들게 된다.  
이 파일들까지 원격저장소에 올라가면 같이 개발하는 다른 팀원들의 설정파일을 건드리게 되어 혼란을 야기할 수 있고, 
용량이 큰 빌드 파일이 올라감으로써 원격레포지터리가 무거워지게 된다.  
이들을 커밋할때마다 제외하긴 귀찮으니 알아서 무시해주게 하는 설정파일이 .gitignore이다.

## .gitignore가 뭔가요?
말 그대로 git에서 무시할 파일들을 정의한 파일이다. 
#### 왜 무시할 파일이 생기는거죠?
- 로컬 설정, 빌드정보, 백업정보등을 저장소에 올려놓지 않기 위해
- 원하지 않는 파일이 업로드 되거나 혹시모를 데이터 충돌을 방지하기 위해
 
## .gitignore 사용해보기
사용법은 매우 쉽다.
.gitignore파일을 생성 한 후 무시하고 싶은 파일 리스트를 아래처럼 두면 된다.  
```
/build
/.localsetting
*.test
```
간단한 프로젝트는 이렇게 직접 .gitignore을 만들어서 사용해도 되지만 규모가 큰 경우는 정의해야할 것이 많아진다.  
그럴땐 [gitignore.io](https://www.toptal.com/developers/gitignore)에 들어가서 본인 환경에 맞는 .gitignore를 생성해 사용하면
아주 편하게 불필요파일을 걷어낼 수 있다. 


[GitHub 사용법](/categories/github/)