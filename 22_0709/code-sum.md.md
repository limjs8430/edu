# ✅원격저장소 활용하기(GitHub) 

> Git 은 '분산버전관리시스템(DVCS)' 입니다. = Git 은 버전, 즉 커밋을 관리합니다.
>
> 분산버전관리시스템은 **원격 저장소(remote repository)**를 이용해 타인과 협업하고, 이전까지의 히스토리를 클라이언트 사이에 공유됩니다.

## 1. 원격 저장소의 종류

- GitHub, GitLab, Bitbucket ...

## 2. 원격 저장소의 기본적인 원리

1. 로컬 저장소에 있던 버전(=커밋)을 원격 저장소로 내보냄

```
$ git puch
```

1. 원격 저장소에 있던 버전(커밋)을 로컬 저장소에 내려 받음

```
$ git pull
```

## 3. [활용] GitHub로 원격 저장소 생성

1. GitHub 에 로그인하고, `create repository` 선택
2. 저장소 이름과 간단한 설명만 작성하고, 하단 `create repository` 선택
3. [경로 설정 1단계] `vs code` 를 켜고 아래의 명령어 입력

```
$ git remote add origin https://github.com/깃헙유저네임/저장소이름.git
```

1. [경로설정 2단계] 아래의 명령어로 원격 저장소 정보를 확인

```
$ git remote -v
```

1. [경로설정 3단계] 아래의 명령어로 원격 저장소에 로컬 저장소의 변경 내역(커밋)을 업로드

```
$ git push <원격저장소이름> <브랜치이름(수업 편의상 master)>
```

## 4. [활용] GitHub 에서 버전 가져오기

1. 복제를 원하는 github repository 에 접속해서 `Code` 클릭
2. 작업하려는 디렉토리에서 VS code 켜고, 아래 명령어 입력

```
$ git clone https://github.com/깃헙계정/저장소이름.git
```

1. 저장소이름으로 새롭게 생성된 파일을 열고, 그 파일의 git 저장소 열기(git bash)
2. 아래 명령어를 입력해 복제된 저장소의 커밋들을 받음

```
$ git pull origin master
```



💡 Clone 과 Pull 의 차이

| clone           | pull                     |
| --------------- | ------------------------ |
| 저장소를 받아옴 | (저장소의) 커밋을 받아옴 |

 💡 github repository 에서 `Code` 를 클릭하면 `Download ZIP` 을 누르고 싶은 충동을 느낄 수 있다. 그러나 이렇게 압축파일을 다운로드하면 최신버전의 '파일 폴더만' 가져오는 것이기 때문에, 버전을 받아오길 원한다면 무조건 `clone` 명령어를 이용하자

------

- 원격 저장소 설정 관련 명령어 정리

| 명령어                         | 내용                               |
| ------------------------------ | ---------------------------------- |
| git clone                      | 원격저장소 복제                    |
| git remote -v                  | 원격저장소 정보 확인               |
| git remote add <원격저장소>    | 원격저장소 추가(일반적으로 origin) |
| git remote rm <원격저장소>     | 원격저장소 삭제                    |
| git push <원격저장소> <브랜치> | 원격저장소에 push                  |
| git pull <원격저장소> <브랜치> | 원격저장소로부터 pull              |







# ✅마크다운 문법 정리

## 1. Heading

- \#의 개수에 따라 h1 ~ h6 까지 표현할 수 있다.

- 볼드체까지 함께 처리되기 때문에 단순히 글자 크기를 조절하기 위해 사용하기보단 글의 제목, 소제목을 표현할 때 활용하는 것이 추천된다.

  💡#바로 다음에 띄어쓰기를 해줘야 정상적으로 작동된다.

## 2. List

**1. 순서가 있는 리스트(ol)**

 시간 흐름이나 위계에 따라 순서를 맞춰 목록을 작성하는 경우,

 텍스트 앞에 숫자를 적는다. (아래 예시 참조)

1. 포유류
   1. 개
   2. 고양이
2. 조류
3. 양서류

 💡`shift + enter` 키로 하위 위계를 계속 작성할 수 있다.

**2. 순서가 없는 리스트(ul)**

 특별히 고려할 순서없이 목록을 작성하는 경우,

- 동물

  - 강아지
  - 독수리

- 식물

  - 해바라기

  - 밤나무

    위와 같이 텍스트 앞에 *나 -를 붙여서 나열한다.

 💡`tab` 키를 이용해서 들여쓰기 조작가능하다.

## 3. Fenced Code block

```
print('hello')
# 주석
```

*backtick 기호 3개씩을 원하는 프로그래밍 언어 앞뒤에 붙여서 작성한다.*

## 4. Inline Code block

```
hello HTML
```

*backtick 기호 1개씩을 작성하려던 코드 이름이나 라이브러리 이름 앞뒤에 붙여서 작성한다.*

## 5. Link

[문자열](https://github.com/code-sum/TIL/blob/master/url) 구조로 링크를 작성한다.

## 6. 이미지

[![sxQSQrmO_400x400](https://github.com/code-sum/TIL/raw/master/gram.assets/sxQSQrmO_400x400-16571594177531.jpg)](https://github.com/code-sum/TIL/blob/master/gram.assets/sxQSQrmO_400x400-16571594177531.jpg)

- [![파일명](https://github.com/code-sum/TIL/raw/master)](https://github.com/code-sum/TIL/blob/master)

 💡`.md` 파일의 원활한 공유를 위해 상대경로를 지정한 경우,

1. 로컬에 저장된 이미지를 Typora 창에 드래그한다.

2. 이미지가 상대경로에 저장된 상태이므로, 작업하던 디렉토리에 'OOO.assets' 형식의 새로운 폴더가 생성된다.

   > [주의] 타인과 마크다운 문서를 공유하고 싶을 때, 새로 생성된 폴더도 함께 공유해야 문서에 첨부한 이미지가 깨지지 않는다.

## 7. Blockquotes (인용문)

인용문이 시작되는 지점에 꺽쇠(>)표시를 붙여준다.

> Nistul is great.

## 8. Table (표)

Typora 상단에 있는 본문(P)를 누르거나, 단축키 `ctrl + T` 를 누른다.

| 이름   | 나이 |
| ------ | ---- |
| 뿡뿡이 | 1살  |

## 9. text 강조

- **볼드체**: 텍스트 앞뒤로 **을 붙여준다.
- *이탤릭체* : 텍스트 앞뒤로 *을 붙여준다.
- ~~취소표시~~: 텍스트 앞뒤로 ~~을 붙여준다.

## 10. 수평선

------

------

3개 이상의 에스터리스크(***), 대쉬(---), 언더스코어(___)를 입력해준다.







# ✅Git 기초 명령어

> 본 문서를 이해하는데 도움이 될 개념을 먼저 정리했습니다.

- 기본 개념 및 용어정리
  - 1통: `working directory`, `modified` *이 단계에 머문 파일은 파일명이 **붉은 글씨**로 표시 됨*
  - 2통: `staging area` (=임시공간), `add` *이 단계에 머문 파일은 파일명이 **초록 글씨**로 표시 됨*
  - 3통: `repository` (=commit)

------

- 작업중인 폴더 내 **새로운 (빈) 폴더** 생성할 때

  ```
  $ mkdir 폴더명
  # mkdic = make directory 의미
  # git은 파일 단위로 변화를 감지하기 때문에, 비어있는 폴더를 새로 생성했다고 해서 add, commit 명령어를 입력할 필요는 없음
  ```

- 작업중인 폴더 내 **새로운 파일** 생성할 때

  ```
  $ touch 파일명
  # 파일명.csv 와 같이 파일명 옆에 원하는 파일형식 입력 가능
  ```

- 작업중인 폴더 내 **하위 폴더로 이동**해서 작업하고 싶을 때

  ```
  $ cd 폴더명
  # cd = change directory 의미
  ```

- 작업중인 폴더보다 **상위 폴더로 이동**해서 작업하고 싶을 때

  ```
  $ cd ..
  ```

- **저장소(repository)**를 처음 만들 때

  ```
  $ git init
  ```

- 작업하고 있던 저장소를 **삭제**할 때

  ```
  $ rm -rf .git
  # GUI에서 [숨은 폴더 표시] 기능을 이용해 .git 파일을 삭제해도 됨
  ```

- 사용자 정보 입력

  ```
  # 본격적으로 버전을 기록하기 전에, 아래와 같은 명령어를 이용해 사용자 정보(commit author)를 입력해야 함
  # username 과 email 은 GitHub와 동일해야 함
  $ git config --global user.name "username"
  $ git config --global user.email "my@email.com"
  
  # 설정한 사용자 정보 내역 확인
  $ git config --L
  $ git config --global --L
  $ git config --global --list
  $ git config user.name
  ```

- **버전을 기록**할 때

  ```
  $ git add . :현재 디렉토리 중 변경된 파일 모두 2통으로!
  $ git commit -m '커밋하고 싶은 메시지'
  # 1통~2통: add
  # 2통~3통: commit
  
  $ git add 파일명 :특정한 하나의 파일만 수정해서 그 버전을 만들고 싶을 때
  $ git add 파일명 파일명 파일명 :복수의 파일을 하나의 버전으로 만들고 싶을 때
  $ git add . :.gitignore에 기재된 것 고려하여 모두 추가
  $ git add * :.gitignore에 기재된 것 상관없이 모두 추가
  # .gitignore 에 대한 상세정보는 본 문서 하단 참조
  ```

- 현재 상태를 확인할 때

  ```
  $ git status :1통, 2통 상태 확인
  $ git log :커밋(=버전) 확인
  
  # log 명령어는 현재 저장소에 기록된 커밋 조회
  $ git log -1
  $ git log --oneline :저장된 커밋들을 간략히 출력
  $ git log -2 --oneline
  ```

- 로컬에서 불필요해진 파일을 삭제한 다음 그 버전을 기록할 때

  ```
  $ git add .
  $ git commit -m 'OOO 파일 삭제'
  # 이렇게 커밋을 한 다음 과거 버전으로 돌아가면, 삭제했던 파일이 되살아남
  $ git push origin master
  ```

- 버전 관리와 상관없는 파일을 제외/hide하고 싶을 때

  *.gitignore 는 Git 이 무시하는 목록이다*

  *Git 저장소에 .gitignore 파일을 생성해 해당 내용을 관리하자*

  1. `.gitignore` 파일 생성

  2. ```
     .gitignore
     ```

      

     파일에 무시하고 싶은 파일들을 적어둠

     - 특정 디렉토리: /true_secret
     - 특정 파일: 1.txt(모든 1.txt), test/1.txt(test 폴더의 1.txt)
     - 특정 확장자: *.csv
     - 예외 처리: !2.csv

  💡[개발 언어](https://github.com/github/gitignore)

  💡[프로젝트에 맞는 .gitignore 파일 만들기](https://gitignore.io/)





1. 브랜치 기초

가지치기를 하기 전에 나무의 뿌리(루트 커밋)를 만들어 주는 과정이 필요하다.

따라서 아래 명령어를 순차적으로 입력해준다. git init,

touch README.md,

git add .

git commit -m 'Init'

*master: 기준이 되는 뿌리 브랜치

git branch : 현재 '브랜치 조회'

git branch example : example 이라는 이름의 '브랜치 생성'

git checkout example : '브랜치 변경'

작업이 다 끝나면 git status 로 확인

git add .

git commit -m '변경 내용'

git log --oneline

이 상태에서 git checkout master 명령어로 브랜치 이동

git log --oneline 으로 재확인하면

example 브랜치에서 작성했던 커밋이 사라져있는 것을 확인

*HEAD: 현재 위치하게 된 브랜치를 알려줌

병합하기

git checkout master :기준이 되는 브랜치로 이동

git merge example

git log --oneline 으로 HEAD의 흐름이 어떻게 생겼는지 확인

브랜치 지우기

git branch -d example

*브랜치를 지워도 지운 브랜치에서 작업했던 커밋이 지워지는 것은 아니다(master에 붙였기 때문)

*실제로 개발할 때 merge 가 완료된 브랜치는 지워버린다

1. 깃헙

*브랜치 이름은 개발을 담당한 사람보단, 기능 이름을 주로 적는다

깃헙으로 merge 작업을 수행했다면, 로컬에서는 별도로

merge 작업을 더하지 않아도 된다.

다만 깃헙에서 merge 해버리면 불필요해진 브랜치는 직접 지워야된다.

컨트롤 l 터미널 정리

과제: 리드미에 수업후기 작성해서 넣어주세요

```
$ git push origin example
# 위와 같이 입력했는데 깃헙에 반영이 안된다면,
# 로컬에서 remote: 부분에 뜬 url을 컨트롤+클릭하면 됨!
```

💡특정 파일에 대한 add 만 취소하고 싶다면?

예시) png 파일, exe 파일을 함께 add 해버렸는데

.exe 에 대한 add 를 취소하고 싶을 때

```
$ git restore --staged f.exe
```

💡마크다운 보고서를 저장하지 않았는데, 내용이 지워져있을 때

어떻게 복구해야할까?

커밋, 푸시, 풀 아무것도 안한 상황

```
$ git status : 파일이 modified 되었는지 먼저 확인
$ git restore 파일명 : modified 이전 상태로 복구해줌
```

1. 모든 변경사항은 로컬에서 하고, 커밋&푸시하는 연습!

내일 아침에 이해도 점검 테스트 예정

예시) git 이 무엇인지 쓰시오