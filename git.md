git init : 현재 디렉토리에 내가 작업을 진행하겠다.(버전관리하겠다)  
	파일을 git의 관리하게 둠  
rm -rf .git : 현재 로컬저장소를 더이상 관리하지 않음.  
ls -al : 현재 디렉토리 파일 목록 보여줌  
vim f1.txt : f1.txt를 편집(+생성)  
	i : 입력모드  
	esc : 입력모드 해제  
	:wq : w=write q=quit 저장하고 끄기  
cat f1.txt : 파일의 내용보기  
git status : 상태표시. 최신화 된 파일이나 상태가 있으면 보여줌  
git add f1.txt : 파일을 관리해라. (새로 생성된 파일이나 새 버전 파일 최신화)  
git config --global user.name xxxxxxx : 누구껀지 이름입력  
git config --global user.email xxxxxxx : 누구껀지 이메일 입력  
git config --global --replace-all user.name xxxxx :유저네임 변경  
git commit -am "xxxx" : a : add하기 m : 뒤에 메시지 입력. 커밋하기  
	--amend : 최근 커밋 내용 수정  
	파일이 변경되고 add하지 않고 commit을 하면 마지막 add한 상태의 파일을 commit하게 된다. 그래서 add의 과정과 commit의 과정을 진행 시켜줘야 하는데 이 두 과정을 합친게 commit -a이다. 이 명령어를 사용하면 현 상태의 파일을 add시킴과 동시에 commit시킨다.  
//cp aaaaaa bbbbbb : aaaaaa파일을 bbbbbb의 이름으로 복사.  
gitignore : 파일 중에 내용이 디버그 할때마다 바뀌어 git에서 관리하기 힘든 파일이 있다.   
vim .gitignore //파일 하나 생성  
해당 파일, 폴더를 작성(vim)  
커밋  
안된다면  
git rm -r --cached .  
git add .  
커밋  
이 세 과정 거치기.  
//한번도 버전관리가 안된(add안한) 파일은 커밋되지 않는다.  
git log --reverse : 로그 처음부터 보기  
git log -p : 로그 보여주기. -p : 버전간 차이점 보여줌. 코드까지 보여줌.  
git log oooo..oooo : 두 주소 사이 비교+ 브랜치 비교 앞에 없고 뒤에있는거 보여줌.  
git log --branches --graph --decorate --oneline :   
//로그에 모든 브랜치를 표시, 그래프로 표현, 브랜치 명을 표시, 한줄로 표시(HEAD->exp) 지금 exp브랜치에 체크아웃 되어있다.  
git diff 주소 : 주소를 기점으로 앞뒤 비교(git log -p 의 축소판)  
git diff oooo .. oooo : 코드 비교//각각의 브랜치 현재상태비교  
  
git reset : 주소이후 모두삭제 (--hard : 묻지말고따지지말고 일단삭제)  
git revert : 주소를 삭제하며 새로운 보전 생성  
  
git branch : 브랜치 목록 보여줌.   
git branch ooooo : oooo에 이름써주기  
git checkout oooo : oooo으로 이동. //커밋 주소를 쓰면 그 때로 이동//tag로 이동할 수도 있음. //git checkout master : 마스터로 이동  
git checkout -b oooo : 브랜치 생성과 동시에 전환  
//브랜치를 생성하면 기존에 있던 디렉토리를 그대로 복사해 온다  
git branch -d ooo : 브랜치 삭제  
git branch -D ooo : 병합하지 않은 브랜치를 강제 삭제  
  
git merge ooo : 현재 있는 디렉토리에서 ooo을 흡수(ooo을 현재디렉토리로 병합)   
브랜치는 그대로.  
//다른 브랜치라도 같은 파일의 이름이라면 코드가 합쳐져버린다.  
*******같은 코드가 수정되었을 경우*******  
<<<<<<<<<<HEAD  
function a(master){  
======  
function a(exp){  
>>>>>>>>>exp  
이런식으로 표현됨.  
======기준 윗부분이 현재 checkout한 부분의 수정사항  
밑에 exp부분이 exp부분의 수정부분.  
꺽새 부분내부를 수정하고 저장하면 코드가 저장됨.  
fucntion a(master, exp){ 라고 써주면 저 상태로 병합.  
  
git stash : 감추기(WIP working in precess)  
브랜치에서 작업을 하다가 다른 브랜치로 가서 수정사항을 커밋하고 싶을  
때기존 브랜치를 커밋 시키지 않으면 다른 브랜치의 커밋도 영향을 받아  
커밋되지 않는다. 이때 작업중이던 브랜치에 git stash로 감추기를 하면 index가  
생성되고(git stash list) 작업중이던 파일의 가장 최근 커밋 상태로 돌아간다.  
이때 다른 브랜치로 옮겨가 작업을 하면 커밋이 가능하다. 그 후 다시 원래   
작업중이던 브랜치로 돌아와 git stash apply 를 해주면 작업중이던 파일이  
그대로 살아난다. 이건 git reset --hard로 삭제를 해도 마찬가지로 살릴 수 있다.  
인덱스가 저장되기 때문.  
shash를 여러번 할 경우 위에것이 가장 최근에 처리한 것이다.  
git stash apply를 하면 가장 위에 stash를 적용한다.(단 drop을 하진 않는다)  
git stash drop 을 통해 가장 최신의 stash를 삭제해준다  
apply+drop=pop 이다. git stash pop을 통해 작업중이던 파일을 살리고 그 인덱스를  
동시에 삭제할 수 있다.  
stash는 tracked되는 파일만 적용한다= add로 버전관리 되는 파일만 stash한다.  
  
---------------------------------------------------------------------------
원격 저장소 생성

remote repository <--> local repository
저장 + 협업
git push --ser-upstream 주소 master
         (master에 앞으로 저장)

git init --bare [name] : 원격저장소에서 수정할 수 없도록 설정.
git remote add [nickname] [path] : 현 저장소에서 원격저장소를 추가
//git push -u origin master : 밑에 설명있음. 윗줄 하고 바로 실행
git remote -v : 원격저장소 보기
git remote remove [nickname] : 원격저장소 삭제
git push
git push --set-upstream origin master

git clone 주소 내주소 : 복제 다른 작업폴더 내 디렉토리로 복사해오기.
이후 git pull

git push -u origin master : 로컬저장소 기준에서 원격저장소로 정보를 보낼 때
오리진의 마스터 브랜치로 보낸다. -u : 로컬과 원격을 연결시켜 다음부터 git push 만 해도 됨


ssh-keygen : ssh키 생성 (엔터세번)
cd ~/.ssh : 기본디렉토리

git tag 1.0.0 : 가장 최근 커밋에 버전 생성.(light weight tag)
git tag -a 1.1.0 -m "oooo" oooo//커밋아이디, master,  (annotated tag)
git tag : 버전만 보여주기
git tag -v 버전 : 버전의 annotated tag 보여줌
git push --tags : 태그까지 올려줌
git tag -d 버전 : 해당 버전 테그 삭제

rm -rf .git : 깃 저장소 취소

git rebase oooo 

* 44fcf51 (HEAD -> master) 5
* 6ce41dc 4
| * 596926c (rb) 3
| * d2bc3fc 2
|/
* 5966f9c 1

* c803946 (HEAD -> master) 5
* 0e02f01 4
* 596926c (rb) 3
* d2bc3fc 2
* 5966f9c 1
이렇게 바뀜

---------------------------------------------------------------------------

다시 정리

# git

* 현재 디렉토리를 원격저장소에 연결

** git remote add <별명>  <주소>

뒤에 나와있는 주소에 현재 디렉토리를 연결시켜라.
그리고 주소가 기니까 <별명>을 사용해라(주로 origin)

** git remote
현재 연결된 원격저장소 목록을 보여줌

여러개의 원격저장소를 연결시켜서 원하는 원격저장소에 저장할 수 있음.

** git remote remove <별명>

해당 원격저장소를 지움.

** git push -u origin master

현재 checkout 되어 있는 로컬저장소 브랜치를  원격저장소<별명>의 master 브랜치로 업로드 시킨다. 
-u : 현재 로컬 브랜치와 원격저장소를 자동으로 연결시켜 앞으로 명령어를 사용하지 않으면 자동으로 해당 저장소 브랜치로 업로드.

----------------------------------------------------------------------

# ssh(Secure SHell)
로그인 없이 원격저장소 이용하기

** ssh-keygen
어떤 말이 나오고 경로가나옴. 경로 기억하기.  엔터 두 번 누르기.
해당 디렉토리로 가면
id_rsa : 비밀 키
id_rsa.pub : 공개 키
두 파일이 생성된걸 알수있음
나는 비밀키를 가지고 있고 공개키는 원격저장소에 보냄. 
원격저장소는 공개키를 가지고 비밀키와 통신해 로그인 필요 없이 자동로그인이 가능해진다.
cat id_rsa.pub
명령어를 치면 머라머라 나오는데 전체를 복사한다.
깃헙 셋팅에
SSH and GPG keys 로 들어간다.
Title에 지역저장소 이름을
key에 id_rsa.pub에서 복사한 내용을 넣어준다.
add ssh key

원격저장소 만들때 SSH로 만든다. 주소를 카피한다
git clone <주소> <만들 디렉토리>
한번도 접속한 적이 없는데 만들거냐 -> yes
git push 하면 id, passwd 입력 없이 잘 들어가짐.
