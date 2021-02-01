# git 초기화
* 각자 맞는 프로젝트 실행
* git init -> 초기화되어서 .git 디렉토리 생성
* * *
# 서버에 올리기
* git add 명령어를 이용하여 필요한 파일을 git관리에 등록, 불필요한 파일은 미등록(.gitignore에서 관리)
* .gitignore 불필요한 것들로 작성 ex).idea
1. 파일등록(add) 
    * ex) git add newFile.js -> newFile.js을 git에 add 하겠다
    * git add * -> 전부 하겠다. 그렇지만 Linux에서는(.) 숨김파일이여서 git add .gitignore 쳐야함
2. 수정 된 상태(modified status)
    * git status -> 지금 상태를 알 수 있는 명령어
3. 수정 된 상태를 다시 등록 (add)
4. 상태 저장 (commit) - 내 로컬(local)서버에만 저장되는 상태
5. 상태 업로드 (push) - 현재 최종 커밋 상태를 원격(remote)서버에 업로드
* * *
# 받는 방법
* pull 현재 브랜치를 서버에서 받아다가 merge까지 해주는 거
* fetch 서버에서 최신변경사항을 받아다가 local에 쌓아주기만 하는거
* * *
# 참고
* git status를 쳤을때, 빨간색으로 되면 commit 할꺼가 아니다.
* git commit -m "log기록" -> local서버에서 올린것
* Windows 환경에서 git 명령 문자열은 꼭 쌍따옴표(" ")를 사용해야 함
* jetbrains 제품에서는 add + commit 한번에 수행 (코드 편집 창에서 Ctrl + K)
* * *
# branch
* git branch -> 현재 branch 리스트 보여줌
* git branch branch_name -> branch 추가
* git checkout branch_name -> branch 전환 
* git merge branch_name -> branch_name에 있는거를 땡겨서온다
    * branch_name에서 수정사항을 master에 병합
* * *
# 원격서버에 올리기
1. github.com 들어가서 로그인 후, new repository 만들어라
2. 최초 등록 git remote add origin <원격 저장소 URL>  -->new repository에 있음
3. 올리기 git push origin master
* * *
# 원격서버 잘못 올렸을 경우(파일삭제)
1. 원격 저장소에 파일 삭제하기
* git rm --cached -r [file Name]
// .idea 폴더 하위의 모든 파일 삭제
   * git rm --cached -r .idea/
// .idea/aa.py 파일 삭제
   * git rm -cached .idea/aa.py
2. 원격 저장소에 적용하기
* git commit -m "Fixed untracked files"
* git push origin master
* * *
# git init 취소(.git지우기)
* rm -r .git (.git 폴더가 삭제 Git 로컬 저장소 지정을 해제) ->우분투 명령어
