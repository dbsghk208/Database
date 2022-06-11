# property
<br>

> **property**
> 

속성  
html DOM  안에서 attribute  를 가리키는 표현

```jsx
  var person = {
	name : "Jason",
	age : 25,
	occupation : "Student",
	getPersonProfile : function() {
		return "Name : " + this.name +
				"\nAge : " + this.age +
				"\nOccupation : " + this.Occupation;

	}
};
```
<br><br>

name age occupation  >> property    
getPersonProfile(위의 함수를 담고 있음)  
<br>

프로퍼티는 object 를 위해서 데이터를 저장한다.  
메소드는 object 가 요청 받을 수 있는 액션  
<br>


```jsx
<div class = 'my-class'> </div> 
```

className  이  property 가 되는것

html 문서 안에서 **class 가 attribute 를 의미**하지만  

**html DOM  안에서는 property  의미**한다.

 Attribute  와 property  구분하는 차이점

attribute 는  html document  

property 는  html Dom tree 안에서 존재합니다.

이것이 뜻하는 것 

attribute 는 정적으로 변하지 않고 , 

property 는 동적으로 그 값이 변할 수 있다는 것 내포
