
## JRE, JVM, JDK 개념 및 차이점
<br>

> JVM   
>

JVM 은 자바가상머신의 약자  

JVM 은 자바 소스코드로부터 만들어지는 자바 바이너리 파일(.class) 를 실행할 수 있음.  
또한 JVM 은 플랫폼에 의존적임  
즉 리눅스의 JVM 과  Windows의 JVM 이 다름(플랫폼에 따라 달라지는 JVM 특성때문)  
단 컴파일된 바이너리 코드는 어떤 JVM 에서도 동작시킬수 있음  
<br>

<JVM 의 역할>    
- 바이너리 코드를 읽는다.  
- 바이너리 코드를 검증한다.  
- 바이너리 코드를 실행한다.  
- 실행환경의 규격을 제공한다.(필요한 라이브러리 및 기타파일)  
<br><br>

> JRE
>

JRE 는 자바실행환경 의 약자  
JVM 이 자바 프로그램을 동작시킬때 필요한 라이브러리 파일들과 기타 파일들을 가지고 있다.  
JRE 는 JVM 의 실행환경을 구현했다고 할수 있음


![JRE2](https://user-images.githubusercontent.com/89206108/173379608-3e291008-18dd-4ca8-897e-f4cacef7ebbb.JPG)
<br><br>

> JDK
>

JDK 는 자바 개발도구 의 약자  
JDK = JRE + 개발을 위해 필요한 도구(javac, java등)들

![JRE](https://user-images.githubusercontent.com/89206108/173379630-e8a9fa95-1fe1-46eb-b74a-48a2285bcd15.JPG)
