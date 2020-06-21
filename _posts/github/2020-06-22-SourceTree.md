---
title: "Gui(SourceTree)로 Git을 사용해보자"
excerpt: "SourceTree를 사용하여 Git을 사용해 보자"
toc: true
toc_sticky: true
categories:
    - github
tags:
    - github
    - sourcetree
last_modified_at: 2020-06-22T10:20:00-09:00
---
강력한 GUI git 관리 툴인 sourceTree를 사용해서 Git을 사용해보자

## SourceTree
강력한 Git 관리 툴이며, JIRA(이슈 관리 툴)를 만든 Atlassian에서 만들었다.
 리눅스 버전을 지원하지 않는게 단점이다.(사실 리눅스에는 아직까진 만족스러운 Git Gui 툴을 찾지 못하였다.)  
한 눈에 필요한 모든 정보들을 확인 할 수 있고, 직관적이여서 관리가 편하다. 

## SourceTree 사용하기
### 1. 원격 저장소를 로컬에 받아오기
본인의 레포지터리를 로컬에 받아오고 싶으면 Remote 탭에서 받아오면 된다.
선택한 저장소의 계정이 소유하고 있는 원격 레포지터리들이 전부 출력되며, 원하는 레포지터리를 선택하면 된다.  
![Remote](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree.JPG)  
원하는 레포지터리를 선택하면 clone에 정보가 입력이 된다.
저장될 디렉토리 지정, clone할 때 체크아웃할 브랜치를 지정할 수 있다.
만약 본인의 레포지터리가 아닌걸 받아오고 싶을땐 clone 탭에 바로 정보를 입력하면 된다.  
![Clone](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree1.JPG)  
clone을 완료하면 아래와 같은 화면이 나온다.
지금까지의 커밋정보들이 나열되며, 마지막 커밋이 수정한 파일과, 어느부분이 변경되었는지 확인 할 수 있다.  
![Main화면](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree2.JPG)  
### 2.파일을 스테이지에 올리고, 커밋하기
탐색기 버튼을 누르면 바로 로컬 레포지터리 디렉토리로 이동할 수 있다.  
파일을 수정을 하면 아래와 같이 커밋하지 않은 변경사항이 생기며, 선택을 하면 변경된 부분을 확인 할 수 있다.  
![diff](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree3.JPG)  
이 때 파일 상태를 누르면 아래와 같이 스테이지에 올릴 파일을 선택할 수 있으며, 
변경내용을 검토하며 스테이지에 올리면 된다.  
![stage](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree4.JPG)  
파일을 스테이지에 올렸으면 커밋 메시지 입력을 한 후 커밋을 하면 되고,
 `origin/<branchName> 에 바뀐 내용 즉시 푸쉬`를 선택하면 원격 저장소에 푸쉬까지 한번에 할 수 있다.  
 ![commit](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree5.JPG)  
### 3.원격 저장소에 push 하기
커밋을 했으면, 아래와 같이 origin이 아닌 로컬 브랜치에 커밋이 생김을 확인할 수 있다.    
 ![checkbeforepush](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree6.JPG)  
이 때 push할 내용이 있다고 알림이 나오게 되며, push를 누르면 푸시할 브랜치를 선택할 수 있다.  
 ![push](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree7.JPG)  
푸시를 하면 origin브랜치와 로컬 브랜치가 같아짐을 확인할 수 있다.  
 ![checkafterpush](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree8.JPG)  

### 4. 원격 저장소에서 pull 하기
패치를 누르면 원격 저장소의 상태를 받아 올 수 있다.  
 ![Fetch](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree9.JPG)  
아래와 같이 원격 저장소가 현재 로컬보다 많이 변했을 때, 추가된 커밋을 확인할 수 있으며, 
pull 받을수 있는 커밋 수를 알림을 받는다  
 ![afterFetch](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree10.JPG)  
pull 버튼을 누르면 여러가지 옵션을 선택할 수 있으며, 원하는 옵션을 선택 후 pull을 받을 수 있다.  
 ![pull](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree11.JPG)  
### 5.브랜치 생성하기
브랜치를 생성할 기준 브랜치로 체크아웃 한 후 브랜치 버튼을 누르면 아래와 같은 화면이 나온다.
이 때 브랜치 명을 지정하며, 기본값은 현재 체크아웃한 브랜치 기준으로 생기며, 
원하는 커밋기준으로도 브랜치를 생성할 수 있다.
 ![createBranch](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree12.JPG)  
브랜치 생성 후 새 브랜치로 체크아웃된것을 확인할 수 있다.
 ![AfterBranch](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree13.JPG)  
### 6. 브랜치 병합하기
작업 후 합치고 싶은 브렌치로 체크아웃을 한 후 병합을 누르면 아래와 같은 화면이 나오며,
 병합을 원하는 브랜치와 커밋을 지정할 수 있다.  
![mergeBranch](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree14.JPG)  
아래와 같이 정상적으로 병합이 된 것을 확인할 수 있다.   
![aftermerge](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree15.JPG)  
### 7. 선택한 커밋으로 돌아가기
작업하다가 소스가 꼬였을 때 원하는 커밋 기준으로 돌아갈 수 있다.  
![reset](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree16.JPG)  
아래와 같이원하는 옵션을 선택을 할 수 있다
![resetoption](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree17.JPG)  
성공적으로 지정한 커밋으로 되돌린것을 확인할 수 있다.
![afterReset](https://raw.githubusercontent.com/always0ne/always0ne.github.io/master/_posts/github/images/SourceTree18.JPG)  

## 정리하기
git을 GUI툴인 SourceTree를 사용해서 편하게 사용하는 법을 배웠다. 
다음 시간에는 commit과 branch 전략에 대해서 소개하겠다.

[GitHub 사용법](/categories/github/)