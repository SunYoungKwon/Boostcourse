# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 2. WEB UI 개발 - FE
### window객체
전역객체이며 생략가능
### 비동기처리 & 콜백함수
특정 코드의 연산이 끝날 때 까지 코드의 실행을 멈추지 않고 다음 코드를 먼저 실행
스택이 비워진 후 실행
```
consloe.log('1');
setTimeout(function() {console.log('2');}, 3000);
console.log('3');

-> '1'출력 '3'출력 3초 후 '2'출력
```
### DOM(Document Object Model)
- DOM Tree: DOM형식으로 저장된 정보
- document: HTML의 최상위 객체
- querySelector: CSS selector를 이용하여 element를 찾음

HTML은 Tree형태로 저장됨
```
document.getElementById("id");      // id값이 "id"인 element
document.querySelector("div");      // HTML문서의 첫번째 <div>
documrnt.querySelector(".class");   // class값이 "class"인 element
document.querySelectorAll("div");   // 문서내 모든 <div>
```
### Event
```
var element = document.getElementById("id");        // element선택
element.addEventListener("click", 함수, false);     // 해당 element를 클릭하면 함수실행
```
  [addEventListener() 참고](https://developer.mozilla.org/ko/docs/Web/API/EventTarget/addEventListener)
### AJAX(Asynchronousb JavaScript and XML)
비동기로 서버로부터 데이터를 가져올 때 사용  
새로고침 없이 서버에서 받아온 데이터로 화면의 일부만 갱신
- JSON(JavaScript Object Notation)  

```
function ajaxTest() {
  var req = new XMLHttpRequest();
  req.addEventListener("load", 함수);
  req.open("GET", "url");
  req.send();
}
```
  [XMLHttpRequest() 참고](https://developer.mozilla.org/ko/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest)  


-----
[>>> 3. JSP - BE](https://github.com/tunaep5/Boostcourse/blob/master/BC_WebProgramming/2_DB%EC%97%B0%EA%B2%B0%EC%9B%B9%EC%95%B1/2-3_JSP-BE.md)
