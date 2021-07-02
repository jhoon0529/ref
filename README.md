## Github cmder 

λ git --version
(깃허브 설치확인-버전확인)

λ git config --list 
(모든 설정 확인)
git config --global -e
(파일로 열어보고 싶은 경우 -e: 에디트)

λ git config --global user.name "아이디"
(user.name 등록)
λ git config user.name
(등록 확인)
λ git config --global user.email "이메일"
(user.email 등록)
λ git config user.email
(user.email 등록확인)

λ git config --global core.autocrlf true
(window는 true, 줄바꿈 시 "\n" 로 통일 - autocrlf)
저장시 "\r\n"에서 \r 삭제 하여 \n 만 전달, 받을 때는 \n만 받음

-------------------------------------------------------------
git [명령어] -option
config/ commit / add

1. 폴더 만들기
만들고 싶은 위치 이동
mkdir [폴더명]
-만든 폴더로 이동 cd [폴더명]

2. Git 생성 (초기화)
git init
-깃 초기화 => .git 숨겨진 폴더 생성 + master (*마스터 브랜치 자동생성)
rm -rf .git
-브랜치 삭제

3.Alias 설정
git config --global alias.[변수] [명령어]
λ git config --global alias.st status
λ git st
λ git st -s (숏으로 줄여서 보기)

4. 도움말 보기(옵션보기)
git [명령어] -h
-------------------------------------------------------------
-------------------------------------------------------------
<<컨트롤 + L (커맨드 창 청소)>> 
<<파일생성 echo>>
λ echo hello world! > a.txt (초기 작성 / 덮어쓰기)
λ echo hello world! >> a.txt (추가 작성)
-echo [파일내용] > [파일명.확장자] 에 담는다.
λ git st
-현재 branch/commit/tracked 상태를 알 수 있음.
<<파일 삭제 rm>>
λ rm a.txt
-스테이지에서는 deleted:    a.txt 로나온다.


<<Stage 에 올리기 add>>
git add a.txt
λ git add *.txt (.txt 확장자 전체)
-git add [파일.확장명] 
-Changes to be committed: (use "git rm --cached <file>..." to unstage)
-Commit 할 준비 된 변경사항, file

==>> Add 후 수정된 파일은 다시 Add 해주어야함
-Changes not staged for commit: 
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   a.txt

λ git add .
-모든 파일을 다시 스테이지로(삭제 포함 갱신개념)


<<Stage에서 내리기 rm --cached >>
λ git rm --cached * ( * : 전체 )

<<스테이지 예외처리>>
λ echo *.log > .gitignore
-echo [내용] > [파일명]
-gitignore 내 적힌 사항은 예외처리한다.
-ignore 된 파일은 없어지고 .gitignore 파일은 업로드할 수 있다.

<<status 관련 변동'내용' 확인>>
λ git diff (워킹디렉토리 변경사항만 확인)
-> diff --git a/[파일명] b[파일명]
->바뀐내용
->인덱스정보

@@ -1 +1,2 @@
 hello java
+add
->(-1은 이전내용, +0 확인할 부분(add)

λ cat c.txt (파일정보)

λ git diff --staged (스테이지 내역 확인)
λ git diff --cached
(둘다 동일함)

<< 커밋하기 >>
git add .
git commit -m "등록제목"
git commit -am "등록제목" (전체)
