# git 명령어 정리
 
- git init: 깃 저장소를 초기화 한다. 이것을 입력한 후에 추가적인 깃 명령어를 사용 할 수 있다.
- git config: 최초에 깃을 설정할때 사용한다. 
- git help: 가장 많이 사용하는 깃 명령어를 보여준다 
- git status: 저장소에 상태를 체크할 수 있다. 저장소 안에 어떤 파일이 있는지, 커밋이 필요한 변경사항 이 있는지, 어떤 브랜치에서 작업 하고 있는지 등 
- git branch: 새로운 브랜치를 만들고, 본인의 변경사항과 파일 추가 등의 타임라인을 만든다. 동료들과 함께 작업하고 본인의 변경사항을 원할때 사용한다 
- git add: 깃이 새 파일들을 지켜보게 한다(새 파일을 추가하진 않는다). 파일을 추가하면, 깃의 저장소 "스냅샷"에 포함된다. 
- git commit: 변경사항을 만든 후 저장소의 "스냅샷"을 찍기 위해 이것 을 입력 한다. 예) git commit -m "Message hear." 형식으로 사용. -m은 명령어의 그 다음 부분을 메시지로 읽으라는 뜻 
- git checkout: 현재 위치하고 있지 않은 저장소를 "체크하웃"할 수 있다. 체크하길 원하는 저장소로 옮겨가게 해주는 탐색명령이다. 예) master 브랜치를 들여다 보고 싶으면, git checkout master 
- git merge: 브랜치 작업을 끝내고, 모든 협업자가 볼 수 있는 master브랜치로 병합 한다. 예) git merge cats는 "cats" 브랜치에서 만든 모든 변경사항을 master로 추가 
- git push: 나의 커밋을 깃허브 온라인으로 보기를 원할때, 이 명령어로 깃허브에 변경사항을 "push"한 다. 
- git pull: 로컬 컴퓨터에서 작업할때, 작업하고 있는 저장소의 최신 버전을 원하면, 이 명령어로 부터 변경 사항을 다운로드한다
- touch - 파일 생성
  - touch text.txt
- rm - 파일 삭제
  - rm test.txt
- git push origin master - 레포에 넣기





# Basic 터미널 명령어



### 작업위치

- `pwd`
  Print working directory; 현재 작업 위치 알려줌.
- `ls`
  list files; 현재의 directory의 모든 파일들을 보여줌.
- `cd ..`
  상위 디렉토리로 이동.
- `cd ~`
  사용자의 홈디렉토리(/Users/hannah)로 감.

- `cd 디렉토리명`
  change directory; 원하는 디렉토리로 이동; 다만 건너뛸 수는 없음. 한 칸씩 단계적으로 들어가야 함.





### 디렉토리 / 폴더

- `mkdir 디렉토리명`
  make directory; 새로운 directory 생성.

- `rm –rf 디렉토리명`
  디렉토리 삭제. 디렉토리와 디렉토리 하위의 모든 파일까지 삭제.

- `cp -R <sourcedir> <destdir>`
  디렉토리 복사.
  Sourcedir: 카피하고 싶은 폴더명, destdir: 옮기고싶은 폴더명.
  검색키워드# mac terminal commands copy directory

  

### 파일

- `cat 파일명`
  파일의 contents를 보여줌.

- `touch .파일명`
  파일 만들기.
  Ex) touch .DS_Store (DS_Store라는 파일 만들기)

- `echo "파일내용" > 파일명`
  내용과 함께 새로운 파일 만들기.
  Ex) echo "project test" > test.html ('project test'라는 내용이 있는 test.html 파일을 생성)

- `파일명 .gitignore`
  무시해야할 소스파일 만들기. 소스파일 버전관리.

- `ls -al | grep .파일명`
  특정 파일 불러오기. 찾고 싶은 파일이 있을 때.
  Ex) ls -al | grep .gitconfig (gitconfig파일 찾기)

  

### etc.

- `ctrl + L`
  터미널 화면 clear (화면이 너무 복잡할 때).

# 터미널로 Git 관리하기



## status

> git status

레포지토리의 상태를 보여주는 명령어.
현재 브랜치, 원격 브랜치, 현재 추적중인 파일, 변경된 파일목록 등이 표시됨.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F2b0987f7-7475-44bf-8d01-1c43927d35f6%2Fimage.png)폴더를 만들어서 git status를 하게 되면 나오는 내용⬆️
`On branch master`: 현재 브랜치는 'master'라는 뜻.
`No commits yet`: 아직 commit한 내용은 없음.

![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fc131b3d8-6534-4d0b-a0e6-9a36db47fe6b%2Fimage.png)Staging area로 들어갈 준비가 된 파일: `index.html`
추가되지 않은 파일(git add가 되지 않은 파일) : `hello.html`
**add되지 않은 파일은 commit이 될 수 없기 때문에 지금 상태로 commit을 하게 되면 여전히 working directory에 남아있게 된다**.

이렇게 현재상태를 확인하면 된다!!!





## add

`add`는 Working directory의 파일을 staging area로 옮기는 명령어.

> git add [파일경로] *명령어에 대괄호`[]`는 입력하지 않음

명시된 파일만 staging area로 추가.
Ex)`git add index.html` : index.html 파일만 staging area로 추가.

> git add .

추가해야될 파일이 다수인 경우, 현재 디렉토리 밑에 있는 추가되지 않은 *모든 파일을 staging area에 한번에 추가*.

> git add -i

![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F5f4fca46-daa5-4a0f-992c-b99feff11c8a%2Fimage.png)![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fcae8ecb5-d4a6-45f2-ad16-3a74b9df6019%2Fimage.png)

대략 위와 같은 모습.
여러가지 명령 프롬프트가 나오게 함. 원하는 액션에 맞는 번호를 바로 입력하면 됨. *다른 사람들과 공동작업을 할 때 특히 이렇게 하는 게 좋음.*





## remove

> git rm –cached [파일경로]

staging directory에 추가된 파일을 다시 working directory로 내려보내는 명령어.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fa2b08e3e-d353-41ae-b7bf-310cdc1407c2%2Fimage.png)`git status`를 입력했을 때 나오는 화면.
괄호 안의 comment처럼 `git rm –cached index.html` 하게 되면 staging area 에서 다시 workind directory로 내려보내게 된다.

> git rm -r --cached .

현재 staging directory에 있는 모든 파일을 한꺼번에 다시 workind directory로 내리기.





## commit

Staging 영역에 있는 파일을 repository에 저장하는 명령어.

> git commit

입력해야할 커밋메시지가 긴 경우에 사용. 줄 바꿀이나 띄어쓰기가 가능. 이 명령어를 입력하면 디폴트 에디터가 출력됨. 에디터에서 메시지를 입력한 후 저장(**`esc + :wq`**)하면 커밋이 됨.

이 명령어를 입력하면 밑의 사진처럼 editor(vim)창이 출력이 됨.
(만약 출력 안되고 modified 어쩌고하는 화면만 보일 경우 **`git commit –a`** 입력하면 아래 화면이 나옴)
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F21ffc5ff-efcc-443d-b359-e585d9aa2c12%2Fimage.png)

여기서 맨 윗줄에 넣고 싶은 메시지(여기서는 `add index.html`)를 입력하고 **esc키**를 눌러서 맨 밑줄로 이동한 다음,
**`:wq`** 를 입력함. *저장 후 나간다는 명령어*.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F27b6afa2-1ca9-44b6-994e-fcf740bce204%2Fimage.png)이렇게 몇 개의 파일/줄이 추가되거나 삭제되었는지 알려준다.

> git commit –m "커밋 메시지"

m은 메시지의 약자. 타이틀정도로 간략하게 메시지를 입력하는 경우에 사용.

> git commit -a–m "커밋 메시지"

working directory에 있는 파일들이 staging area를 거쳐서 커밋되는 것이 일반적이지만, 이 명령으로 staging area를 거치지 않고 바로 커밋할 수 있게 됨.



### **<커밋이 가능한 경우>**

git의 경우, 리포지토리 영역에 있는 파일이라도 한번 수정을 하게 되면 다시 working directory형태로 내려오게 됨.
이 경우에는 수정을 하고 바로 이 명령문을 통해 커밋을 할 수 있는 것.

예를들어,

현재 커밋이 완료된 index.html 이라는 파일이 있는 상태에서
`echo "<html> </html>" > index.html`로 index.html파일 내용을 변경하고 (아무 내용이 없었던 파일에 html태그를 추가한 것)
`git status`로 상태를 조회하면 아래처럼 modified 된 파일이 있다고 알려줌.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F708b2630-2ff7-4e11-9b83-0d2c80efb044%2Fimage.png)이 파일의 경우, 한번 커밋이 되었던 파일이기 때문에 staging area를 거치지 않고 바로 커밋을 진행할 수 있음.
이 화면이 뜨면 `git commit –a –m "Added html tags"` 라고 입력해서 커밋을 진행할 수 있게됨.



### **<커밋이 불가능한 경우>**

이 명령어를 쓸 수 있는 건, *한 번이라도* staging area를 거쳤던 파일에 한해서이다!
새로운 파일을 생성했다면 `git commit –a-m "커밋메시지"`를 한다고 해도 그 대상에 포함되지 않음.

만일 staging area를 거치지않은 파일을 commit하려 한다면
**`nothing added to commit but untracked files present`**
라는 메세지로 커밋된 것은 없지만 staging area에 있지 않은 untracked files가 있다고 알려줌.





## log

저장소에 있는 commit 이력을 조회하는 명령어.

> git log

현재 브랜치의 커밋이력을 디테일하게 볼 수 있음. 타이틀 메시지, 컨텐츠 메시지, 누가커밋 했는지 등 전반적인 정보를 준다.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fa2c33e54-6d16-4075-8d9e-57c33b8510b8%2Fimage.png)`git commit` 으로 제목 + 내용까지 상세하게 기록한 커밋은 아래처럼 내용까지 보여짐![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F3746aa9f-e002-4201-9fbe-8e7ba45beb3a%2Fimage.png)조회가 끝나면 **`'q`**로 화면나가기

> git log --oneline

말 그대로 한줄(oneline으로)로 간단하게 보여달라는 명령어. 커밋이력 중 커밋 ID, 타이틀 메시지(에디터로 커밋했을 때 첫번째 줄에 있는 정보/ 혹은 -m뒤에 따라오는 정보)만 조회.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F195852c6-4126-4471-9894-ec839632f9d4%2Fimage.png)

> git log --oneline --decorate --graph --all

**모든 브랜치의 커밋이력을 조회**하게 됨. 브랜치가 한 개라면 단순하게 한 줄로 표시가 됨.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F5a5a4c8d-64ab-4fe2-8a39-8bb76ea42246%2Fimage.png)

브랜치가 여러 개인 경우에 적합. (사진은 master에서만 작업했기 때문에 이렇게 보여짐)
`--oneline` : 한 줄로 간단하게
`--decorate` : 어떤 브랜치인지 --all을 빼고 입력하면 master를 포함해 **모든 브랜치** 내용을 볼 수 있음
(**더 자세한 예시는 하단의 checkout 부분에 有**)

> git log -- [파일경로]   *❗️띄어쓰기 주의❗️*

특정 파일의 변경 커밋내용만 조회.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F12e110db-c674-4846-819d-5ae243970e7b%2Fimage.png)위 화면은 `git log -- index.html`로 출력된 결과.





## diff

다른 커밋과 working directory를 비교하는 명령어.
**`-`**표시는 삭제된 부분, **`+`**표시는 더해진 부분을 나타냄.

> git diff

현재 브랜치의 마지막 커밋과 working directory의 차이점 비교.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fe8297b2e-d6db-4162-8ddb-0f4b785ceeb0%2Fimage.png)highlight된 부분처럼 어떤 부분이 달라졌는지 알려줌.

> git diff [Commit ID]   *명령어에 대괄호`[]`는 입력하지 않음

특정 커밋과의 차이점 비교.
(명령어에 대괄호`[]`는 입력하지 않음)
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Ff4c0b67b-972e-407a-961d-b338f69c8d7f%2Fimage.png)예를 들어 사진처럼 id No.`0f97c10`을 비교해본다고 하면 이 명령은 아래와 같이 **모든 파일의 커밋 정보를 다 알려줌**.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fe8f3e29c-28dc-4ab2-baa3-7f811e3beffa%2Fimage.png)만약에 특정 커밋과 특정 파일만을 비교하고 싶다면 파일 경로를 같이 입력해주기.
(아래 명령어처럼)

> git diff [Commit ID] -- [파일 경로]

특정 커밋의 특정 파일이 스냅샷이 찍힌 시점과 현재 working directory의 파일 내용이 어떻게 다른 지 비교.

- 입력 예시:![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F7170d361-6777-4409-af80-7363e54e9846%2Fimage.png)
- 결과:
  ![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F9009356a-4529-41ad-9227-bc5405106692%2Fimage.png)





## branch

브랜치 생성, 수정, 삭제를 하는 명령어.

> git branch

브랜치 목록 조회.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F58fce111-9863-4423-936a-45c7acc45b77%2Fimage.png)위 화면은 'develop'이라는 브랜치와 'master' 브랜치가 있는 상태.
브랜치명 앞에 **`\*` 이 붙어있는 곳이 현재 위치**.

> git branch [브랜치명]

브랜치 생성.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F77bfa5af-e248-4292-9af2-df8a345fd62d%2Fimage.png)'git_branch' 라는 디렉토리 생성.

> git init

특정 디렉토리를 git repository(master)로 지정하기.
`cd git_branch`로 git_branch 디렉토리 내부로 옮겨간 후에`git init`을 하게되면,
해당 디렉토리를 **git repository로 만듦과 동시에 master가 생성된다**.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F08970d09-1763-4aa7-bead-6e6a0f733d0e%2Fimage.png)이 때 ❗️주의할 점❗️
아래 화면처럼 아무런 커밋을 하지 않은 상태에서 브랜치를 만들려고 하면 오류가 난다!!
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F495cd50d-f6a4-42db-b5c7-3e4d3d87f73f%2Fimage.png)⬆️`git log`로 커밋내역을 조회했을 때 어떤 commit도 되지 않은 상태임을 확인할 수 있음.
이 상태에서 'develop'이라는 브랜치를 생성하려고 하면 나오는 메세지: `fatal: Not a valid object name: 'master'`

> git branch -d [브랜치명]

브랜치 삭제.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Ff9fd3198-4d4d-4880-886d-b2db7484eba5%2Fimage.png)'develop' 브랜치 삭제.
`git branch`로 모든 브랜치를 확인해보면 남은건 'master'브랜치 뿐.

> git branch -m [oldName][newName]

브랜치 이름변경.
`oldName`: 현재 브랜치명
`newName`: 변경할 브랜치명
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F1c2aecf8-3867-4f10-80a2-e61a006e0c5b%2Fimage.png)⬆️'develop'브랜치를 'test'로 변경.
`git branch`로 확인해보면 'test' 로 정상변경 됨.

> git checkout -b [브랜치명]

브랜치 **생성과 동시에 만들어진 브랜치로 바로 옮겨가는** 명령어.





## checkout

워킹 디렉토리의 소스를 특정 커밋으로 변경하는 명령어. 쉽게 말하면 내가 사용할 브랜치를 지정하는 행위.

> git checkout [브랜치명]

특정 브랜치로 워킹 디렉토리 변경. 브랜치 이동하기.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F23f48279-0f0c-4100-bbed-239e123ea9c2%2Fimage.png)⬆️checkout 전 상태 : master 브랜치에 있음(`*`이 앞에 붙은 브랜치가 현재 위치).

![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F77310e1b-3207-441c-b802-587ec1a27081%2Fimage.png)⬆️develop 브랜치로 현재 위치 변경(명령어: `git checkout develop`). develop 브랜치로 옮겨온 상태.
`nothing to commit, working tree clean` : develop 브랜치를 만들고 나서 **소스(파일)수정을 전혀 하지 않았기 때문에 master랑 develop은 완전히 똑같은 상태**(똑같이 커밋되지않은 random.html을 하나씩 가지고 있는 상태)임을 나타냄.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F3909707e-5403-4d2c-815b-8ba5fa817795%2Fimage.png)⬆️develop브랜치의 random.html파일에 태그 추가(소스 변경) 후 master로 checkout.
이 상태는 아직 add & commit을 하지 않은 상태이기 때문에 **이 상태 그대로** master브랜치로 random.html이 옮겨짐.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F61805e9b-9aa8-4684-b212-e320bab1602c%2Fimage.png)master브랜치로 가서 cat random.html으로 파일 본문 보게 되면 **수정한 상태가 그대로 남아있음**(여기도 add & commit은 되지않음).
이 상태에서 add & commit하면 **master 브랜치에만 커밋이 됨**.
develop 브랜치에는 **처음 생성된 상태 그대로 보존되어 있음**.

즉, 브랜치가 *생성될 시점의 그 모습 그대로* 유지가 된다. 생성된 이후에 부모 브랜치에서 어떤 것을 수정한다고 해도 자식 브랜치의 내용이 바뀌지는 않는 것!! 그래서 작업을 할 때는 *어느 브랜치의 워킹디렉토리에서 작업을 했는지* 반드시 기억해야한다!!!

만일 어느 브랜치에서 작업했는지 기억이 나지 않을 때는 `git log --graph –-oneline –-decorate –-all`로 모든 브랜치의 변경된 사항 조회해 볼 수 있음.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F8d8ded1e-5edb-4e0d-8dfe-f5e41ea9fdf2%2Fimage.png)

다른 예로,
master의 자식브랜치 중 하나인 release 브랜치에서 about.html이라는 파일을 만들고 add&commit을 한 후,
master에 다시 가서 `ls`로 모든 파일 목록 확인해보면 master에서는 about.html파일을 **찾을 수 없다**.
처음에 만든 index.html만 보여짐.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fd91d489a-71d6-4fca-87db-895fd013b705%2Fimage.png)![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F41d34795-e35b-43cd-843c-41357a2102fd%2Fimage.png)⬆️`git log --graph --oneline --decorate --all`로 그래프를 보면 **그래프 상에서 master브랜치가 가장 밑에 있기 때문에 위에 위치한 release브랜치에서 만든 파일들이 master에서 보여지지 않는 것**!![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fe8a071fd-a30b-4cde-a43a-fe4d877ef95e%2Fimage.png)같은 원리로 develop브랜치에서도 about.html이 보이지 않음.

그래서,

⭐️ **파일을 만들거나 수정할 때 주의할 점** ⭐️
✔️ 현재 내가 작업하고 있는 브랜치가 어디인지 git branch로 꼭 확인하기!!
✔️ 엉뚱한 디렉토리에 작업파일 저장되지 않도록 주의하기

> git checkout [Commit ID]

특정 커밋으로 워킹 디렉토리 변경.
커밋이 완료된 상태에서 특정 커밋으로 가고 싶을 때는, `git log --oneline`으로 Commit ID를 확인해서 옮겨가면 된다.
![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F85b4372c-3c71-403d-b7d7-d71fac3f68a6%2Fimage.png)⬆️지금 master브랜치에 있는 index.html파일은 저렇게 태그가 추가 되어있는 모습.
만약에 그 전 커밋된 **cc97215**로 가고 싶다면 `git checkout cc97215`로 옮겨갈 수 있음![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fac58eba2-4595-4b75-9ce3-a980ad621e0f%2Fimage.png)현재는 **cc97215**로 옮겨온 상태.
여기에서 다시 `cat index.html`로 파일 내용을 확인하면 Index.html에 아무 내용도 없음.
즉, **cc97215**이라는 커밋에는 index.html에 아무것도 없었던 상태.
하지만 또 다시 master로 돌아가면,![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F703b971f-5226-48a9-a2b0-7bd4863ccb7a%2Fimage.png)⬆️이렇게 추가가 되어있는 걸 확인할 수 있음.

> git checkout [Commit ID] -- [파일경로]

특정 파일을 해당 브랜치 또는 커밋 상태로 변경.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fe4d98534-4893-42c0-b0f8-80f49533316c%2Fimage.png)위 예제에서 보면 master브랜치의 index.html파일에는 태그들이 추가가 되어 있는 상태.
예를 들어, 만약에 **7800fa1**라는 커밋이 잘못된 커밋이라 다시 **cc97215**상태(태그가 없는 상태)로 되돌리고 싶다면,
`Commit ID -- 파일명` 으로 변경하기![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fd2a1472d-7bbd-40a3-988e-c2fd39c93e4d%2Fimage.png)⬆️변경 후에는 이렇게 index.html이 태그 추가 전 상태로 돌아가서 아무것도 없는 걸 확인 할 수 있음.





## merge

다른 두개의 소스를 병합하는 명령어.

> git merge [브랜치명]

Git에서는 병합하는 방법이 **2가지** 있음.
\1) **rebase** - 이력을 다듬어야 할 때. Git의 flow를 정확히 이해해야 사용할 수가 있다.
\2) **merge** - 단순히 명령만 입력하면 병합이 됨.

예를 들어 develop브랜치를 master로 병합한다고 할 때,![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Ffc9ab787-e44c-421e-a275-79db0c4511e5%2Fimage.png)
\1. 제일 먼저 `git checkout master`로 옮겨가고,
\2. `git merge develop`을 하게 되면 develop이 master에 병합이 됨.

### ⭐️**CONFLICT 주의**⭐️

merge가 항상 잘 되는 것은 아님!!!
다른 브랜치에 같은 파일이 다른 내용으로 있으면 충돌하기 때문에 merge가 되지 않음!! 사용자가 저장을 원하는 버전을 **수동으로 지정**해줘야 함!
이렇게 자동으로 merge되지 않는 부분을 "**CONFLICT**"라고 함.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F4cf8e585-ad5f-433e-8ee7-02bfc2478c14%2Fimage.png)따라서 `git status`로 진행 중간중간 상태확인하는 습관이 필요함. conflict 시에는 아래처럼 경고 메시지가 나옴.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fc48fa38c-0e8c-4a0f-8e3d-e15776a41344%2Fimage.png)
같은 부분을 서로 다르게 수정했을 때 나오는 conflict 화면:![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Feeacf5e6-0e55-4eed-9829-b7a127c86a54%2Fimage.png)이 때 `git status`로 상세내용을 살펴보면 아래와 같이 보여짐:![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F5b784099-1d27-4928-8dc9-1aa4818c46c4%2Fimage.png)이럴때는 `vim 파일명`으로 충돌된 파일에 들어가서 충돌되는 부분 확인:![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F3bb861d6-7323-4452-a247-a19fec6e9eeb%2Fimage.png)![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fea85c46a-0e43-4111-a832-b8049754d692%2Fimage.png)develop브랜치에 있는 부분이 틀렸다고 가정하고 hightlight되어 있는 부분들을 모두 삭제![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F90ccb9ca-1490-4ce0-8a8e-a2bb2354dc5b%2Fimage.png)이렇게 필요없는 부분 모두 지운후에 `:wq`로 다시 저장![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F3b822fe9-1fd4-42dc-817f-91adf4d6b158%2Fimage.png)그리고 다시 `git add` & `git commit`으로 커밋을 해주면 완벽하게 고쳐짐.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F16809119-ee40-4f29-93a5-7e95c1d63760%2Fimage.png)수정을 완료한 후,
`git log –-decorate –-graph` 로 그래프 형태를 조회해보면,![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2Fd5b965d0-e16a-488f-943e-f13264fa3825%2Fimage.png)화살표가 develop브랜치에서 master로 merge되는 모습을 확인할 수 있음❗️





## vim

터미널에서 파일 내용(본문)을 수정하는 명령어.

> vim [파일경로]

(내용 추가 후) `esc` + `:wq` 로 **저장**

**파일이 있는 곳**으로 가서 위 명령어 입력하면 밑 화면처럼 수정할 수 있는 vim화면으로 넘어감. ⬇️`vim index.html`한 모습.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F0688f986-d5ed-40fa-a012-ab3f063477d4%2Fimage.png)추가할 내용 적어 넣고 저장은 `esc`키 + `:wq` 로!





## remote add

로컬 repository를 원격 repository와 연동을 하려면 로컬 저장소에 원격 저장소 URL을 등록해줘야 한다.
즉, 로컬 저장소에 원격 저장소 URL을 등록해서 **연동**하는 명령어.

> git remote add [alias별칭][gitURL] *alias는 별명을 만드는 명령어. 명령어를 단축시키기 위한 별칭을 만드는 것.

Ex. `remote add origin https://github.com/ha3158987/repository-testing`

보통 alias별칭은 default인 'origin' 그대로 쓰는 경우가 제일 많지만 바꾸고 싶다면 위 명령어를 입력하면서 alias별칭 자리에 원하는 이름을 적어넣으면 된다!

1. 버전관리를 하고자 하는 프로젝트의 디렉토리를 만든 후, `git init`으로 initialize 하기
2. 그리고 바로 `git remote add 별칭 git리포지토리url` 로 추가
3. 그 다음에 `git remote –v`로 조회하면 밑 화면처럼 alias이름, git repository url 순으로 연결이 된 게 보여짐.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F9dc8cf0e-0f1c-4b42-87c5-5959fc8f7f37%2Fimage.png)





## fetch & pull

원격 repository에 있는 내용을 로컬 repository로 다운로드 하는 명령어.

> git fetch [alias별칭][브랜치명]

Ex. `git fetch origin`

1. 먼저 `git remote -v`로 로컬 repository와 원격 repository의 연동현황을 조회하고,
2. `git fetch github`으로 다운로드 해오기
   ![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F31ce06e7-4c8e-4718-b580-6d52059690e6%2Fimage.png)

참고로 fetch명령어는 working directory에 변경을 주지는 않음.
반면, pull은 fetch와 같은 동작을 수행하지만 **원격저장소의 내용을 로컬 저장소로 받고, 자동으로 merge 까지 수행함**(fetch + merge의 효과). Working directory에 바로 반영됨.

> git pull [alias별칭][브랜치명]

Ex. `git pull origin`

이렇게되면 **로컬에 만들지 않은 파일들**(예를 들면 README파일이나 License 파일 등)**도 merge 하면서 같이 저장이 된다**❗️





## push

로컬 repository의 내용을 원격 repository로 업로드 하는 명령어.

> git push -u [alias별칭][브랜치명]

Ex. `git push –u origin master`
(origin이라는 repository에 master브랜치의 현재 소스를 올리고자 할 때)

리포지토리 생성 후 나오는 화면 중에 아래 화면에 나온 부분이 기존에 있는 리포지토리를 업데이트 하는 가이드라인 ⬇️![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F79a4722c-5719-4a42-a955-06c87edc2d4e%2Fimage.png)

정상적으로 push가 완료 되면 아래 화면처럼 보여짐.![img](https://velog.velcdn.com/images%2Fgrinding_hannah%2Fpost%2F7901948d-0727-4b38-b189-664c5e06d402%2Fimage.png)





## clone

공개된 원격 저장소에서 다운로드를 하는 명령어.

> git clone [url]

Ex. `git clone http://github어쩌고`
단순히 **복제**한다고 생각하면 된다.