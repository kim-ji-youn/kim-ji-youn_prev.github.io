---
title: "Git & Github"
date: 2021-02-10
categories: ETC
comments: true
tags : [git, github]
toc: true
description: 더 이상 미룰 수 없다. Git & Github  
---
더 이상 미룰 수 없다. Git & Github   

## Git
[생활코딩](https://opentutorials.org/module/3733)의 강의를 바탕으로 정리한 내용입니다.      

### Git1
#### 1. 수업소개
Git은 대표적인 버전 관리 시스템이다.   
소스 코드를 관리하기 위하여 사용하는 것이 Git이다. 

#### 2. git을 구경합시다!
**git의 3대 목적**
* 버전관리(version)
* 백업(backup)
* 협업(collaborate)

#### 3. git의 목적1 - 버전관리
같은 파일에 수정을 하더라도 버전 생성을 통해 문서/파일들의 변경 사항을 계속 반영할 수 있게 된다. 

#### 4. git의 목적2 - 백업
* 불확실한 것: 언제 고장날지 모른다
* 확실한 것: 언젠가는 고장난다...
--> 자신의 컴퓨터에만 파일을 저장하는 것은 언젠가 파일을 유실할 수 있다는 가능성을 내포하고 있다는 것..

* 로컬(지역) 저장소: 내 컴퓨터에만 있는 저장소
* 원격 저장소: 파일을 백업해 둔 온라인의 다른 저장소
* **commit**하여 새로운 버전을 (로컬 1)에 저장하고, **push**하여 원격 저장소에 저장, **pull**하여 같은 파일을 (로컬 2)에서 동기화하여 작업 가능!

#### 5. git의 목적3 - 협업
* push: 로컬 저장소에서 원격 저장소로!
* pull: 원격 저장소에서 로컬 저장소로!

* 두 사람이 같은 파일을 수정하는 경우?
* 두 사람이 같은 행을 수정하는 경우?
---> git을 통해 해결! 덮어쓰기와 같은 불상사를 방지해준다..

#### 6. git의 종류
* Git: 명령어로 git 제어
* Github: 단순한 사용, 단순한 기능 
* TortoiseGit: window에서만 사용 가능
* SourceTree: 복잡하지만 강력한 기능

### Git2 - 버전관리
#### 1. 수업소개
* Git: GUI를 사용하지 않는 command line(-> POSIX CLI1)을 활용하여 사용

#### 2. 설치(Windows)
* <https://git-scm.com/> 에서 다운로드
* Git Bash로 콘솔 화면 열기

#### 3. 버전관리의 시작
특정한 디렉토리의 버전 관리를 위한 저장소를 초기화!
* `git init .` : 현재 디렉토리를 git에 버전 관리하도록 저장소를 초기화(initialize repository)
 * 디렉토리 내부에 `.git` 디렉토리가 생성됨
 
#### 4. 버전 생성
* Working Tree: 수정하고 있는 파일들
 * 새로운 버전이 만들어지기 전 단계의 파일들, 작업 중인 파일들
 * `git add FILE_NAME` 명령어를 통해 버전 관리하고 싶은 파일들을 staging area로 이동
* Staging Area: 버전을 만드려고 하는 파일들
 * 버전으로 만들어 저장소에 저장할 파일들, 버전을 생성할 때, staging area에 있는 파일들만 모아 하나의 버전을 생성, commit하고 싶은 파일들
 * `git commit -m MESSEAGE` 명령어를 통해 버전 관리하고 싶은 파일들을 repository로 
* Repository(저장소): 버전이 저장되는 곳, 만들어진 버전

* `git status`: 파일의 버전 관리 상태(working tree status)
 * `No commits yet'
  * `Untracked files`: 파일을 아직 버전 관리 대상으로 설정하지 않았을 때 나타나는 메시지 (-> git add 명령어를 이용하여 파일을 staging area로 이동)
  * `Changes to be committed` : 버전 관리 대상인 파일들이 있음을 나타내는 메시지 (-> git commit 명령어를 이용하여 repository에 버전을 생성)
 * `On branch master`
  * `nothing to commit, working tree clean`: 버전 관리 대상 파일을 모두 commit한 상태, staging area에서 repository로 파일들이 모두 이동.  
  * `Changes not staged for commit` : working tree에서 수정 사항이 있음을 알려주는 메시지 (-> git add 명령어를 이용하여 stageing area로 이동)
  * `Changes to be committed`: staging area에 버전 관리 대상 파일들이 있음을 나타내는 메시지 (-> git commit 명령어를 이용하여 repository에 버전 생성)
  
* `git add FILE_NAME`: working tree에서 생성/수정된 파일을 staging area로 이동(add to staging area)
* `git commit -m '<message>'`: staging area에서 repository로 이동하여 버전 생성(create version)
* `git log`: 수정사항 히스토리를 보여줌, 'q'를 눌러 빠져나올 수 있음. (show version)

## GitHub
마찬가지로 [생활코딩](https://opentutorials.org/module/4636)의 강의를 바탕으로 합니다.
* **Repository(Repo) 저장소**: 각 프로젝트를 위한 소스코드 저장소
  * **Public vs. Private** : public은 오픈소스 저장소, private은 일부 무료로 가능!
  * **README.md** : 프로젝트를 소개하는 역할을 하는 파일
  * **.gitignore** : 프로젝트에서 사용하는 언어/개발환경에 따라서 버전 관리에서 제외시켜야하는 파일의 리스트
* clone or download
  * clone: git을 이용할 때 활용
  * download zip: 단순하게 소스 코드가 필요할 때 활용
* commit: 제출!
  * 초록색: 추가
  * 빨간색: 삭제
