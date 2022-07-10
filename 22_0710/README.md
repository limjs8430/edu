# 7월 10일 주간 정리

## 매우매우 정리가 잘되어있는 
## 김준환님 정리자료
- https://hvvany.github.io/

### 복습 내용
#### Branch
- Master(main) : 배포 가능한 상태

- Develop(main) : 개발 진행 중인 상태

- Hotfix(supporting) : 배포한 버전에 문제가 있을 때 신속하게 대응하기 위함

- Feature(supporting) : 기능별 개발 (ex 네이버 웹툰, 네이버 파이낸셜 등 )

- Release(supporting) : 개발 완료 이후 QA/Test 통해 얻은 정보로 minor bug fix 위함

- 생성 $ git branch branch_name
- 이동 $ git checkout branch_name
- 생성 및 이동 $ git checkout -b branch_name
- 목록 $ git branch
- 삭제 $ git branch -d branch_name
- 그래프 확인 $ git log --oneline --graph

#### Branch Merge
##### 각 branch에서 작업을 한 이후 버전을 합치기 위해서는 일반적으로 merge 명령어를 사용한다
- Merge 명령어 $ git merge branch_2_name      "branch_2 를 master 에 merge 하겠다"
