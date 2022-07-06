
## 2022.07.04
로컬이 있을때 Lunch 아이콘 클릭

<br>

Launch 

웹 브라우저로 실행할 경우 url 을 입력하는 창이 팝업되고  
입력한 url 선택한 웹 브라우저에서 실행한다.

<br>

Quick View 

활성화된 뷰가 Form 편집 뷰일 경우 Quick View 실행할 수 있습니다.   
Project Explorer가 활성화된 상태에서 선택된 트리 아이템이 Form 파일일 경우에도  
QuickView를 실행할 수 있습니다.  

<br>


참고사이트  

http://docs.tobesoft.com/development_tools_guide_nexacro_17_ko#3ec343bd3f0692c0


<br><br>

## 2022.07.05

**<순서>**

**넥사크로 검색 조건(데이터셋) > Controller > serviceImpl > xml > serviceImpl > Controller > 넥사크로 그리드**

<br>

그리드를 만든다음 그리드 자체는 어떤 데이터를 넣을지 모르니깐  
넥사크로에서 데이터셋을 설정을 해주고  
(그리드에 들어갈 칼럼을 일일이 데이터셋에 만들어준다. )

그러면 그리드와 데이터셋 맵핑은 properties > binding  > binddataset 에 맵핑시켜준다.

<br>

아웃 데이터셋이 뒤에 붙는 주소값으로 연결되는것

<br>

## 2022.07.06 

**transaction** 

Application 영역에 정의된 Dataset 의 데이터를 갱신하기 위한 서비스를 호출하고,   
트랜잭션이 완료되면 콜백함수를 실행하는 메소드





