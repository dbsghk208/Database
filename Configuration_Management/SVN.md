
**형상관리**

**소스의 변화를 끊임없이 관리하는 것**


## SVN 

<SVN>

SubVersion  
  
소스의 저장소를 서버로 두고   
작업하는 PC를 클라이언트로 연결하여  
소프트웨어 개발시 소스의 수정과 변경사항을 관리할 수 있는 도구  

작업 내역 커밋시 소스 변경 사항과 히스토리가   
즉시 서버로 전송되고 저장이 되다보니 관리가 용이하며   
과거의 수정내역과 히스토리 파악이 용이해짐    
  
버전관리도구 중 하나로 설치와 구성이 그리 어렵지 않은 것이 특징이다.    
svnserve 라는 svn 서버를 설치하면 된다.   

  
<br> 
  
**<용어>**

  - Trunk
  
  프로젝트에서 가장 중심이 되는 디렉토리   
  개발소스를 commit 했을때 개발 소스가 모이는 장소.  
  소스와 파일 포함  
  
  모든 개발 작업은 trunk 디렉토리에서 이루어지며   
  trunk 디렉토리 아래에는 바로 소스들의 파일과 디렉토리가 들어가게 된다.  
  
<br> 
  
  - Revision
  
  수정된 버전이라는 의미로,   
  클라이언트가 Repository 에 새로운 파일, 수정 등을   
  commit 할때마다 번호가 하나씩 증가한다.  

<br>
  
  - Head
  
  Repository 에 저장된 최신 revision 을 의미한다.  
  누군가에 의한 가장 최근에 commit 된 revision   
  
<br>
  
  - Base
  
  클라이언트가 checkout, update 등의 명령을 통해   
  Repository 로 부터 내려받은 revision 을 의미  
  
  이 revision 을 가지고 클라이언트는 수정 및 커밋을 하게 됨.  
  
  만약 head 와 base 가 다르다면  
  커밋이 거부되고 update를 먼저 수행해야 commit 이 가능해진다.
  
  내가 update한 후 소스 코드를 수정하고 있는 상황에서 다른 사람이 커밋하여 revision 이 증가한 경우  
  head 는 다른사람이 commit 한 revision 이 되어 내 소스코드가 이전 revision 이 된다.
  
  
<br><br>
  
**<명령어>**
  
  - Checkout 
  
  저장소에서 소스를 받아오는 명령어  
  받아온 소스에는 소스 뿐만 아니라 버전관리를 위한 파일도 같이 받아옴  
  
  - Export
  
  Checkout 과 달리 버전관리 파일을 뺀 순수한 소스만 가져오는 명령어로 마지막에 사용
  
  - Commit 
  
  로컬 저장소의 체크아웃 한 소스의 변경된 내용(수정, 파일추가, 삭제 등) 을   
  저장소에 저장하여 갱신하는 명령어  
  Revision 이 1 증가
  
  - Update
  
  체크아웃해서 받은 소스를 서버 저장소의 최신 소스 버전으로 업데이트 하는 명령어  
  소스 수정이나 commit 하기 전에 한번씩 해주는게 좋음  
  
  - Revert
  
   로컬 저장소의 코스 토드 내용을 이전 상태로 돌리는 명령어  
  
<br><br>  
  
**<SVN vs Git>**
  
  - 둘의 가장 큰 차이점
  
  svn 은 개발자가 자신만의 Version History 를 가질 수 없다.  
  local History 를 이용하긴 하지만 일시적이고   
  자신이 몇일 전 까지에 한해 작업한 내역은 확인 가능하지만 버전관리가 되지는 않음  
  
  
<br><br> 
  
## SVN 사용방법
  
  1. TortoiseSVN 설치 
  
  2. 탐색기에서 작업할 폴더를 선택하고 마우스 우클릭하여   
    [TortoiseSVN] -> [TortoiseSVN Repository Browser] 주소를 입력한다.  
    svn://아이피/svn/trunk/주소
  
  3. 팝업창 폴더에서 해당 오브젝트를 선택 > 우클릭 > Checkout 메뉴 선택
  
  4. SVN 에 저장되어 있는 폴더와 파일들이 현재 디렉토리에 생성됨.
  
  5. 생성된 폴더에서 우클릭 > SVN Update를 누르면 다른 사람이 Commit 한 내용을 가져올 수 있음
  
  <br>
  
&nbsp;&nbsp;&nbsp;이클립스에서 update 하는 방법     
&nbsp;&nbsp;&nbsp;-> synchronize 탭에서 해당 프로젝트에서 우클릭 > synchronize 클릭  
&nbsp;&nbsp;&nbsp;&nbsp;그러면 해당 목록들 다 나옴   
&nbsp;&nbsp;&nbsp;&nbsp;프로젝트명에서 우클릭 > update 클릭하면 변경내역(다른분들 작업한 내역)   
&nbsp;&nbsp;&nbsp;&nbsp;다 업데이트 할 수 있음  
  
&nbsp;&nbsp;&nbsp;**update 아이콘**  
  
&nbsp;&nbsp;&nbsp;<img src= "https://user-images.githubusercontent.com/89206108/177898540-7a44d0bb-0248-48d8-9144-44f1d28919bf.png" width="50" height="50">

 <br> 
  
  6. 생성된 폴더에서 우클릭 > SVN Commit 을 누르면 본인이 수정한 파일 SVN 서버에 업로드 할 수 있음
  
&nbsp;&nbsp;&nbsp;**commit 아이콘**  
  
&nbsp;&nbsp;&nbsp;<img src= "https://user-images.githubusercontent.com/89206108/177898771-fdf69e00-74cd-4f42-95e3-d36fe8eab697.png" width="50" height="50">
 
  
  
  
<br><br>  
  
  참조사이트
  
  https://codedosa.com/653
  
  https://velog.io/@gillog/SVNSubversion-%EA%B8%B0%EB%B3%B8
