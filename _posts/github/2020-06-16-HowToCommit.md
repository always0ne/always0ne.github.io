---
title: "Git 에서 Commit 하기"
excerpt: "깃 저장소를 생성해본 후 커밋을 해보자"
toc: true
toc_sticky: true
categories:
    - github
tags:
    - github
last_modified_at: 2020-06-16T12:02:00-09:00
---
앞의 게시글에서 Git과 GitHub에 대해서 소개를 했으니 
이번 게시글에서는 Git의 자주 쓰이는 기능의 사용법을 설명하고자 한다.  
우선은 Git을 사용하는데 필수적인 개념에 대해 알아보고, 커밋을 해보자.  

## 레포지터리(Repository)
Git에서 Repository는 Git이 관리되고 있는 영역이라고 생각하면 된다. 
Git에서는 두가지의 저장소를 제공한다.
- 원격저장소(Remote Repository)  
원격 저장소(GitHub, GitLab, Bitbucket 등) 서버에서 관리되고 있는 깃 저장소이다.  
- 로컬 저장소 (Local Repository)  
실제 작업하고 있는 PC의 깃 저장소이다.  
보통 로컬 저장소에서 작업을 하며, 원격저장소로 푸쉬한다. 
보통은 원격저장소가 협업용으로 많이 사용되기 때문에 
로컬 저장소에서 충분히 검토를 하고 정리해서 올려야 한다.

## 커밋(Commit) 
작업 단위의 버전이라고 생각하면 된다. 수정내역, 수정시간, 커밋 메시지를 기록한다.  
버그 수정, 기능 추가 등의 의미가 있는 변경이 일어났을때마다 커밋을 하고, 
커밋 메시지에 수행한 작업에 대해 설명을 해놓으면 미래의 나 혹은 같이 작업하는 다른사람들이
코드를 분석하는데 훨씬 수월하며, 버그가 발생했을때도 빠르게 추적이 가능하다.
  
## Git을 사용해서 저장소를 관리해보자
### 1.Git저장소 만들기  
```
mkdir gitTutorial
cd gitTutorial
git init
dir /a
2020-06-16  오후 10:24    <DIR>          .
2020-06-16  오후 10:24    <DIR>          ..
2020-06-16  오후 10:24    <DIR>          .git
```
작업 디렉토리를 생성하여 이동 후 `git init`을 사용해서 git 저장소를 만든다.   
.git 디렉토리가 생겼으면 정상적으로생성된것이다.   
이 디렉토리가 삭제되면 Git 저장소 정보가 전부 날아가니 조심해야한다.

### 2.Git 변경내용 커밋하기

```
git add MyFirstCommit.txt

git commit -m "내 첫번째 커밋"
[master (root-commit) fdbc838] 내 첫번째 커밋
 1 file changed, 1 insertion(+)
 create mode 100644 MyFirstCommit.txt

git log
commit fdbc838ffb473b192209d5a55f45dcf9d522d93f
Author: always0ne <si8363@soongsil.ac.kr>
Date:   Tue Jun 16 22:38:11 2020 +0900

    내 첫번째 커밋
``` 
Git 저장소에서 작업을 하고 `git add FileName`을 하여 파일을 스테이지에 올린다.
 만약 모든 파일을 스테이지에 올리고 싶으면 `git add .`을 하면 된다. 
 여기서 스테이지는 커밋을 할 변경점 리스트라고 생각하면 된다.  
파일을 스테이지에 올렸으면 `git commit -m "커밋메시지"` 을 하여 커밋을 하면 된다.  
커밋 로그를 확인하고 싶을 땐 `git log`을 해서 확인 할 수 있다.

### 커밋하기 전에 사용하면 좋은 기능
- 작업중 현재 내가 수정한 부분을 확인하고 싶을때는 `git diff`를 하면 된다.
```
git diff
diff --git a/MyFirstCommit.txt b/MyFirstCommit.txt
index a701303..cbdc9aa 100644
--- a/MyFirstCommit.txt
+++ b/MyFirstCommit.txt
@@ -1 +1 @@
-Hello Git ~~
\ No newline at end of file
+Hello Git ~~!!
\ No newline at end of file
```

- `git add`명령을 할 때 -p 옵션을 주면 
아래와 같이 변경된 점을 검토한 후 스테이지에 올릴 수 있다.
```
git add MyFirstCommit.txt -p
diff --git a/MyFirstCommit.txt b/MyFirstCommit.txt
index a701303..cbdc9aa 100644
--- a/MyFirstCommit.txt
+++ b/MyFirstCommit.txt
@@ -1 +1 @@
-Hello Git ~~
\ No newline at end of file
+Hello Git ~~!!
\ No newline at end of file
```

## 정리하기
git 저장소 생성하기 `git init`  
git 현재 변경한 내용 확인하기 `git diff`  
git 변경내용 스테이지에 올리기   
`git add <올릴 파일명(전부올리고싶으면 *)> -p`  
git 변경내용 커밋하기 `git commit -m "커밋메시지"`  
[GitHub 사용법](/categories/github/)