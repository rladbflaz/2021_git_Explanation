# git과 github의 차이  

**git** : 지역 저장소를 만들고 파일, 코드 등을 관리하는 작업  
**github** : 내가 로컬에서 git으로 관리하는 자료를 다른 사람과 공유하거나 백업해둘 수 있는 웹사이트


### <git 사전지식>  
- 저장소는 파일이나 디렉토리를 저장하는 장소임.  
- 변경 이력을 관리하고자하는 디렉토리 등을 저장소의 관리하에 두는 것으로, 그 디렉토리에 있는 파일 등의 변경 내역을 기록할 수 있음.  
- 저장소는 자신의 컴퓨터에 있는 "로컬 저장소"고, 서버 등 네트워크에 있는 "원격 저장소(github)" 의 2개가 있음.  
- 기본적으로 로컬 저장소에서 작업을 수행하고 그 결과를 원격 저장소에 저장함.

# **config**  
1) git을 막 설치한 상태임
2) 내 github 정보를 등록하고 싶음
3) git config --global user.name rladbflaz 를 입력해서 내 이름과  
   git config --global user.email youro1228@naver.com 를 입력해서 내 이메일을 등록함


- git config --global user.name "이름" : 이름 등록
- git config --global user.email "이메일" : 이메일 등록

- git config user.name : 등록한 이름 확인
- git config user.email : 등록한 이메일 확인

- git config --list : 설정한 모든 것을 확인  

![config](https://user-images.githubusercontent.com/54675015/117530708-9d05b500-b019-11eb-8d3f-353195341862.PNG)

# **init**  
1) $mkdir swtask2 -> $cd swtask2 를 입력해 swtask2 디렉토리에 들어와있는 상태(아무 파일도 존재하지 않음)
2) github에 업로드 하기 위해 파일들을 로컬저장소에 저장할 디렉토리를 정해야함  
3) git init 명령어를 이용해 swtask2 디렉토리를 git 저장소로 변환함    
git init을 성공적으로 실행했다면 Initialized empty Git repository in ~ 이 출력됨.  

git을 이용하기 위해 가장 먼저 입력해야하는 명령어.  

    현재 디렉토리를 git 저장소로 변환하는 명령어  

![init](https://user-images.githubusercontent.com/54675015/117510493-1f18be00-afc7-11eb-9ea3-0793f9127e9a.PNG)

# **add**  
1) 현재 내가 작성한 파일이 있음.  
2) 이 파일을 github에 업로드하고 싶음.  
3) 그러나 github에 업로드하기 위해서는 몇 가지 입력해야하는 명령어가 있음.  
그 중 add가 제일 먼저 입력하는 명령어임.  
사용자가 컴퓨터에서 업로드하고 싶은 파일을 결정해서 git add [파일명] 을 입력함.

ex) git add test.md ![add](https://user-images.githubusercontent.com/54675015/117509482-49697c00-afc5-11eb-9228-d576cd6a5e7f.PNG)


    작업 디렉토리에 있던 파일을 commit 명령어를 이용해 로컬저장소에 옮기기 전에 add 명령어를 이용해서 인덱스에 추가함. 이때, 인덱스는 저장소에 commit할 준비를 하기 위해 변경 내용을 임시로 저장할 위치임.  

    - git add [file_name]  


### *에러 ! !*  
fatal: pathspec 'file_name' did not match any files 이 출력된다면  
터미널이 해당 파일이 있는 경로에 있는지 확인할 것  

[옵션]
- git add * : 디렉토리에 있는 모든 파일을 staging area로 옮겨짐

# **commit** 
1) github에 업로드할 파일을 git add한 상태임
2) add한 파일을 github에 업로드하고 싶음
3) commit은 github에 업로드하기 위해서 입력해야하는 몇 가지 명령어 중 git add 다음에 입력하는 명령어임.    
git add를 통해 인덱스에 추가된 파일을 git commit -m "메세지" 를 입력해 commit해야함.  

commit은 파일이나 디렉토리의 추가 또는 변경을 저장소에 기록하는 작업임.

- git commit -m "new"  
이때,  " "사이에는 원하는 메세지 입력하면 됨

![commit](https://user-images.githubusercontent.com/54675015/117538300-8d4d9700-b040-11eb-9484-cb1a60904845.PNG)

# **status**  
1) git add 또는 git commit을 한 상태임
2) git add을 입력한 경우는 인덱스에, git commit을 입력한 후엔 로컬 저장소에 어떤 파일이 추가되어 있는지 궁금함.  
3) 이때 git status를 입력하면 알 수 있음.

git add '파일' 후에 git status를 입력하면 
Changes to be committed : ~ commit할 준비가 된 파일들(git add 된 파일)     
![status(new)](https://user-images.githubusercontent.com/54675015/117538235-31830e00-b040-11eb-972f-22fdf4daf44c.PNG) 

Changes not staged for commit : ~ commit할 준비가 되어있는 파일들 중 수정사항(수정, 삭제 등)이 있는 파일들(git add 되었지만 수정이 일어난 파일)    
![status(modified)](https://user-images.githubusercontent.com/54675015/117538247-42338400-b040-11eb-8919-0554abbca263.PNG)  

Untracked files : ~ untracked된 파일들(디렉토리 내에 존재하지만 git add 명령어가 이루어지지 않은 파일들)  
![status(untracked)](https://user-images.githubusercontent.com/54675015/117538256-51b2cd00-b040-11eb-9ed2-29c98706fc9e.PNG)


을 확인할 수 있음  

git commit -m "메세지" 후에 파일이 추가되어 있는지 확인하는 명령어  
![status(commit)](https://user-images.githubusercontent.com/54675015/117538282-773fd680-b040-11eb-9ffb-5c4671023859.PNG)

# **remote**  
1) git에 내 github를 저장하고 싶음
2) commit한 파일들을 github(원격 저장소)에 반영하기 위해 내 github repository의 주소를 알려줘야함.  
3) git remote add origin https://github.com/rladbflaz/sw2 명령어를 입력해서 git에게 알려줌. ![remote](https://user-images.githubusercontent.com/54675015/117538351-c259e980-b040-11eb-8026-e8446c549991.PNG)
이 명령어는 git push 전, 한번만 입력하면 됨.

    - git remote add [이름] [url] : 원격 저장소 추가
    - git remote rm [이름] : 원격 저장소 제거
    - git remote : 원격 저장소의 이름 목록 표시
    - git remote -v : 원격 저장소에 대한 자세한 목록보기

# **push**  
1) 원격 저장소 파일 업로드를 위해 git add -> git commit 까지 입력한 상태임  
2) github에 작성한 파일을 업로드하고 싶음.   
3) 이제 git push origin master만 입력하면 github에 바로 반영이 됨. 


    로컬저장소(내 컴퓨터)의 변경 사항을 github에 있는 원격 저장소에 반영하기 위한 명령어

    - git push origin master  
위 명령어를 입력했을 때, 다음과 terminal에 다음과 같이 출력됨 ![push](https://user-images.githubusercontent.com/54675015/117538696-54162680-b042-11eb-836a-a8a094a66300.PNG)

github 사이트에 접속해서 해당 repository 카테고리를 main->master로 변경하면 다음과 같이 commit했던 파일들이 원격저장소에 업로드된 것을 볼 수 있음 ![push(github)](https://user-images.githubusercontent.com/54675015/117538706-5d06f800-b042-11eb-9c26-e2482e577f59.PNG)

---
## **[브랜치에 push]**  
1) 현재 sub1 브랜치에 있음.  
2) master 브랜치말고 새로 생성한 sub1 브랜치에 파일을 업로드 하고싶음.  
3) 업로드하고싶은 파일을 commit함.  
git push origin sub1 을 입력해서 브랜치를 푸쉬함.  
![branchpush](https://user-images.githubusercontent.com/54675015/117538429-1fee3600-b041-11eb-9242-1672da4f4005.PNG)  
github repository에 가면 브랜치가 푸쉬된 것을 볼 수 있음.  
![branchpush(github)](https://user-images.githubusercontent.com/54675015/117538446-30061580-b041-11eb-8a54-b5000e4de7f1.PNG)  

    - git push origin [브랜치이름] : 브랜치를 github에 업로드

# **branch**  
1) 작성한 파일이 있음.  
2) 현 시점에서 이 파일을 여러 버전으로 나눠서 코딩해보고 싶음.  
3) 먼저 git branch를 입력해보면 현재 branch 목록을 볼 수 있음.   
![branch](https://user-images.githubusercontent.com/54675015/117538489-6348a480-b041-11eb-8a3a-15e67675c92d.PNG)  
\* master 하나만 출력되는데 이것이 기존 branch임.  
    현재 브랜치에는 * 이 붙음. 이것은 브랜치가 master 것이고 현재 브랜치도 master임을 나타냄.  

새 브랜치를 만들고 싶음.  
git branch sub 를 입력하고 git branch를 입력하면 sub 브랜치가 생성된 것을 볼 수 있음. ![branch(sub)](https://user-images.githubusercontent.com/54675015/117538497-6cd20c80-b041-11eb-80de-d7d212efdfb2.PNG)

새로 만든 브랜치는 원 브랜치의 현 상태를 그대로 가져감.

    - git branch : 브랜치 목록을 보고 싶거나 현재 어떤 branch에 위치하고 있는지 알고싶을 때 사용하는 명령어
    - git branch [이름] : 새로운 브랜치를 생성
    - git branch -d [이름] : 브랜치를 삭제

# **checkout**  
1) 현재 master 브랜치에 있음.  
2) sub 브랜치로 이동해서 작업하고 싶음.  
3) git checkout sub를 입력하면 sub 브랜치로 이동됨.  
![checkout](https://user-images.githubusercontent.com/54675015/117538540-a145c880-b041-11eb-88e4-df4afbd99a9c.PNG)  


    - git checkout sub : 생성된 sub 브랜치로 이동
[옵션]  
git checkout -b [이름] : 새로운 브랜치 생성 + 생성한 브랜치로 바로 이동  
![checkout-b](https://user-images.githubusercontent.com/54675015/117538546-ab67c700-b041-11eb-8c56-354d458dad2c.PNG)  

# **pull**  
1) 로컬 저장소와 원격 저장소의 내용이 다른 상태임  
2) 로컬 저장소의 sub1 브랜치를 원격 저장소에 맞춰 갱신하고 싶음.  
3) git checkout sub1를 입력해 sub1로 이동함.  
git pull을 입력하면 원격 저장소의 변경 내용이 로컬 저장소에 받아짐.  
- 로컬 저장소의 모든 변경 사항이 반영되어 있는 상태에서 `새로운 변경 사항이 있는 원격 저장소의 커밋 파일`을 로컬로 가져오는 경우는 단순히 'fast-forward' 병합이 이루어짐.
- 그러나 `로컬 저장소의 master 브랜치에서도 변경 사항이 생긴 경우`, 양 쪽의 변경을 통합할 필요가 있음. 이때 pull을 실행하여 소스를 병합할 수 있음. 충돌하는 변경이 없을 경우 자동적으로 병합 커밋이 만들어지지만, 충돌이 있는 경우 충돌난 부분을 수동으로 해결한 다음 직접 커밋해줘야햠.

> git pull은 공동 개발에서 유용하게 사용됨.  

    - git pull : 원격 저장소의 데이터를 로컬 저장소에 가져와 병합

# **merge**  
1) 현재 sub 브랜치에 있음.  
2) sub 브랜치 결과를 master 브랜치에 병합하고 싶음.  
3) git checkout master 를 입력해 master 브랜치로 이동함.  
git merge sub 를 입력하고 ls를 입력하면 sub에서 만든 test3.md 파일이 추가된 것을 볼 수 있음. ![merge](https://user-images.githubusercontent.com/54675015/117538736-82940180-b042-11eb-92b5-feb5b318345f.PNG)
이것을 github에 푸쉬함.  

    각 브랜치의 마지막 커밋 두 개, 브랜치의 공통 조상 커밋 총 3개의 커밋을 비교하여 새로운 커밋을 만들어 병합을 수행함

# **rebase**  
1) 많은 git merge를 해서 지저분한 커밋 히스토리가 생김
2) 브랜치를 병합하고 싶은데, 지저분한 커밋 히스토리를 보고 싶지 않음. 마치 다른 브랜치가 없었던 것처럼 프로젝트의 작업 내용이 하나의 흐름으로 유지됐으면 좋겠음
3) 아래 사진과 같은 명령어 입력할 경우 한줄로 재배치된 깔끔한 커밋 히스토리가 됨
![rebase](https://user-images.githubusercontent.com/54675015/117537890-ad7c5680-b03e-11eb-85f6-cfb7ace8e770.PNG)  

한 브랜치에서 다른 브랜치로 합치는 방법은 두 가지가 있음. 하나는 merge이고, 다른 하나는 rebase임.  
rebase 방식을 사용해서 병합한다면, 작업하면서 남겼던 commit 중 불필요한 것들은 생략시키고 필요한 commit만 남겨서 master에 병합하기 때문에 master의 commit은 항상 깔끔하게 관리된다는 장점이 있음.
똑같은 병합이지만, 나중에 master의 commit을 볼 때 깔끔하게 볼 수 있어서 여러 명이 협업할 때 유용함.

$ git checkout [브랜치이름]  
$ git rebase master  
$ git checkout master  
$ git merge [브랜치이름]  

# **tag**  
1) 여러 작업을 통해 한번의 과정을 끝낸 상태임
2) 소스 버전을 임의로 정하고 싶음
3) git tag v1.0 을 입력하면 다음과 같이 태그가 생성됨  
![tag](https://user-images.githubusercontent.com/54675015/117511695-26d96200-afc9-11eb-9e2f-27a3658f3d3d.PNG)

Git 에서는 일반적으로 이름 정보만을 갖는 `태그(Lightweight tag)`와 보다 상세한 정보를 포함하는 `주석 태그(Annotated tag)`가 있음

- **Lightweight 태그**는 단순히 버전같은 태그이름만을 남기는 태그임  
$ git tag [태그명] // 태그 생성   
$ git tag //생성된 태그 확인  

- **Annotated 태그**는 태그 만든 사람의 이름, 이메일, 태깅 날짜, 태그 메시지까지 저장하며 GPG(GNU Privacy Guard)로 서명까지 가능함.  

    - tag -a 와 -m 옵션 사용  
    - 태그 확인은 $git show [태그명]

    ![taganno](https://user-images.githubusercontent.com/54675015/117512386-78362100-afca-11eb-9617-2c98fb2f6814.PNG)

    - 태그를 원격 저장소에 push : git push origin [태그 이름]  
    - 모든 태그를 push : git push origin --tags  
    ![tagpush](https://user-images.githubusercontent.com/54675015/117512928-89cbf880-afcb-11eb-94d5-bd20334f844e.PNG)

    다음과 같이 githug에 적용된 것을 볼 수 있음  

    ![taggit](https://user-images.githubusercontent.com/54675015/117512992-ac5e1180-afcb-11eb-952a-d5c1d4b6d97f.PNG)
    
# **log**  
1) new를 commit한 상태
2) 지금까지의 commit 기록을 알고싶음
3) git log를 이용하여 알 수 있음  
![log](https://user-images.githubusercontent.com/54675015/117513383-884f0000-afcc-11eb-86e7-4c143af355ae.PNG)

- 로컬 저장소의 commit 히스토리를 탐색하는데 사용하는 명령어  
- 지금까지의 커밋 기록들이 쭉 출력되며, 가장 위에 나오는 내역이 가장 최근 내역임을 알 수 있음  
- 기록에는 SHA-1 체크섬, 저자 이름, 저자 이메일, 커밋 날짜와 시간, 커밋 메시지가 포함됨

[옵션]
- git log -p -[숫자] : 최근 [숫자]갯수의 커밋 조회
- git log --stat : 기존의 로그에서 간략하게 어떤 파일에서 수정이 일어났는지 추가적으로 보여줌

# **clone**  
1) 작업할 파일도, 디렉토리도 존재하지 않는 상태
2) 내 github 저장소의 데이터를 가져오고 싶음
3) git clone https://github.com/rladbflaz/swtest 입력하면됨  

    ![clone](https://user-images.githubusercontent.com/54675015/117515028-2d1f0c80-afd0-11eb-93e6-3376dd5a39c7.PNG)

    C:\Users\User\Desktop\sw2 경로에 swtest 디렉토리가 복사된 것을 볼 수 있음 (안에 파일도 복사됨)
    ![clonefile](https://user-images.githubusercontent.com/54675015/117515166-6e172100-afd0-11eb-8764-868ea96f8fb5.PNG)

내 github 뿐 아니라 다른 사람들의 github를 clone할 수 있음.  

git 저장소를 쓰는 방법은 두 가지가 있음. 하나는 로컬 디렉토리를 하나 선택해서 git 저장소로 적용하는 방법이고, 또 하나는 위와 같이 다른 어딘가에서 git 저장소를 clone하는 방법이 있음.

    - git clone [url] : 해당경로에 디렉터리(url에서 마지막 / 뒤의 문구가 디렉토리 이름이 됨)를 만들고 그 안에 .git (숨김파일) 디렉터리를 만듦. 후에 저장소의 데이터를 모두 가져와서 자동으로 가장 최신 버전을 가져옴.
    - git clone [url] [생성할 디렉토리 이름] : 지정된 디렉토리 이름이 아닌 다른 디렉토리 이름으로 clone

# **reset**  
1) 방금 "apple"을 commit 한 상태(push한 경우에도 해당)
2) 방금 한 commit을 이전의 commit으로 되돌리고 싶음
3) git reset --hard [커밋ID] 를 입력함. 이때 커밋ID는 $git log를 입력했을때 commit~ 이후에 나오는 일련번호의 앞6자리임. 이것을 복사해서 붙여넣으면 됨  
![resethard](https://user-images.githubusercontent.com/54675015/117536905-b833ed00-b038-11eb-9912-2ae94c5b262b.PNG) 
commit했던 apple이 삭제되고 hi상태로 되돌아 온 것을 볼 수 있음  


> reset은 애초에 commit 하지 않은 것처럼 예전 커밋으로 브랜치를 옮기는 것임

[옵션]
- git reset --hard [일련번호6자리] : 원하는 부분으로 돌아간 후 그 부분 이후의 내역을 모두 삭제함. (파일이 순서대로 a,b,c,d 상태로 있는 경우 d에서 b로 돌아온다면 c, d가 삭제됨)
- git reset --mixed [일련번호6자리] : 원하는 부분으로 되돌아감. 이후에 변경된 내용에 대해서는 남아있지만, 인덱스는 초기화됨. git add를 통해 변경된 내용 추가해야함.
- git reset --soft [일련번호6자리] : 원하는 부분으로 되돌아갔지만, 이후의 내용이 지워지지 않고, 해당 내용의 인덱스가 그대로 남아있음. 바로 다시 커밋할 수 있는 상태로 남음.


|명령어|사용 여부|
|---|---|
|[add](https://github.com/rladbflaz/sw2/blob/main/README.md#add)|O|
|[branch](https://github.com/rladbflaz/sw2/blob/main/README.md#branch)|O|
|[checkout](https://github.com/rladbflaz/sw2/blob/main/README.md#checkout)|O|
|[clone](https://github.com/rladbflaz/sw2/blob/main/README.md#clone)|O|
|[commit](https://github.com/rladbflaz/sw2/blob/main/README.md#commit)|O|
|[config](https://github.com/rladbflaz/sw2/blob/main/README.md#config)|O|
|[init](https://github.com/rladbflaz/sw2/blob/main/README.md#init)|O|
|[log](https://github.com/rladbflaz/sw2/blob/main/README.md#log)|O|
|[merge](https://github.com/rladbflaz/sw2/blob/main/README.md#merge)|O|
|[pull](https://github.com/rladbflaz/sw2/blob/main/README.md#pull)|O|
|[push](https://github.com/rladbflaz/sw2/blob/main/README.md#push)|O|
|[rebase](https://github.com/rladbflaz/sw2/blob/main/README.md#rebase)|O|
|[remote](https://github.com/rladbflaz/sw2/blob/main/README.md#remote)|O|
|[reset --hard](https://github.com/rladbflaz/sw2/blob/main/README.md#reset)|O|
|[status](https://github.com/rladbflaz/sw2/blob/main/README.md#status)|O|
|[tag](https://github.com/rladbflaz/sw2/blob/main/README.md#tag)|O|

