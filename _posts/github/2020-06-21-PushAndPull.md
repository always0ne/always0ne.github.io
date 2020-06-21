---
title: "Git 에서 원격 저장소 사용하기"
excerpt: "local git을 github에 올려보자"
toc: true
toc_sticky: true
categories:
    - github
tags:
    - github
last_modified_at: 2020-06-21T10:20:00-09:00
---
이전 게시글들 에서 Git의 필수기능들을 배웠다. 이제 원격 저장소에 레포지터리를 올려서 협업을 해보자

## 원격저장소
서버에 git을 호스팅 하여 공유하는 것을 말한다. 대표적으로 GitHub, BitBucket, GitLab이 있으며, 
GitHub가 가장 대중적이며, GitLab는 서버에 직접 설치해서 사설서버로 운영할 수 있다.

## 원격 저장소 사용하기
### 1. 리모트 저장소 추가하기
```
git remote add origin https://github.com/always0ne/gitTutorial.git
```
`git remote add <원격저장소 별칭> <원격 저장소 주소>`를 하면 리모트 저장소를 추가할 수 있다.
 보통 원격 저장소 별칭을 origin으로 많이 한다.
### 2.현재 로컬 레포지터리에 등록된 리모트 저장소 확인하기
```
git remote
origin
```
`git remote`로 현재 로컬 레포지터리에 등록된 리모트 저장소를 확인 할 수 있다.
### 3.원격 저장소에 올리기
```
git push origin master
Fatal: HttpRequestException encountered.
Counting objects: 6, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (6/6), 497 bytes | 0 bytes/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To https://github.com/always0ne/gitTutorial.git
 * [new branch]      master -> master
```
`git push <원격저장소 별칭> <원격 저장소 브랜치>`로 로컬 레포지터리의 커밋을 원격 저장소에 올릴 수 있다.
### 4. 원격 저장소에서 받아오기
```
git pull origin master
Fatal: HttpRequestException encountered.
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
From https://github.com/always0ne/gitTutorial
 * branch            master     -> FETCH_HEAD
   969e8c1..2e75901  master     -> origin/master
Updating 969e8c1..2e75901
Fast-forward
 MyFirstCommit.txt | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```
`git pull <원격저장소 별칭> <원격 저장소 브랜치>`로 원격 저장소의 최신 커밋을 받아올 수 있다.

### 5.원격 저장소를 로컬에 받아오기
```
mkdir clone
cd clone

git clone https://github.com/always0ne/gitTutorial.git
Cloning into 'gitTutorial'...
Fatal: HttpRequestException encountered.
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 9 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (9/9), done.
Checking connectivity... done.
```
`git clone <원격 저장소 주소>`를 하면 원격 저장소를 로컬로 가져올 수 있다.

## 정리하기
리모트 저장소 추가하기  
`git remote add <원격저장소 별칭> <원격 저장소 주소>`  
등록된 리모트 저장소 확인하기  
`git remote`  
원격 저장소에 올리기  
`git push <원격저장소 별칭> <원격 저장소 브랜치>`  
원격 저장소에서 받아오기  
`git pull <원격저장소 별칭> <원격 저장소 브랜치>`  
원격 저장소를 로컬에 받아오기  
`git clone <원격 저장소 주소>`  

이제 git을 사용하는데 정말 필수적인 명령어들을 배웠다. 추후 업데이트 할 예정이지만
고급기능들은 [Git 공식 홈페이지 메뉴얼](https://git-scm.com/book/ko/v2)을 참고하자.  
다음 시간에는 Gui로 간편하게 지금까지 배운 기능을 사용하는 법을 소개하겠다.   

[GitHub 사용법](/categories/github/)