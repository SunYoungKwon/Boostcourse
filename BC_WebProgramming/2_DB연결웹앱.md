# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 1. JavaScript - FE
### 변수
  - var, let, const
### || 'or연산자'
  ```
  var name = "Kim";
  var myName = name || "default";     // name값이 있으면 name으로 아니면 default로

  -> myName은 "Kim"
  ```
### 삼항연산자
  ```
  var data = 5;
  var result = (data > 10) ? "yes" : "no";      // 조건 ? true : false

  -> result는 "no"
  ```
### 비교연산자
  ==보다 ===(타입까지 비교)를 사용하기
  ```
  0 == "0";     // -> true
  0 == false;   // -> true
  0 === "0";    // -> true
  ```
### 타입체크
  - toStrig.call을 이용하여 결과값 매칭
  - 문자나 숫자는 typeof이용 가능
### 문자열 method
  ```
  "ab:cd".split(":");           // -> ["ab", "cd"]
  "ab:cd".repalce(":", "$");    // -> "ab$cd"
  "   abcde   ".trim();         // -> "abcde"
  ```
### 함수표현식 vs 함수선언문
  ```
  // 함수표현식
  var a = function() {
    return value;
  }

  // 함수선언문
  function fun() {
    return value;
  }
  ```
### 호이스팅(Hoisting)
- hoist: 끌어올리기  

Javascript에서 모든 변수 선언은 위로 끌어올려진다. But 끌어올려지는 것은 선언 뿐! 할당은 아님!
함수선언문은 위치에 상관없이 전체코드에서 유효함
  ```
  // 예제 1
  function getX() {
    console.log(x);     // undefined
    var x = 10;
    console.log(x);     // 10
  }

  // 예제 2
  functoin getX() {
    var x;
    console.log(x);     // undefined
    x = 10;
    console.log(x);     // 10
  }

  -> 예제1과 예제2는 같다!
  ```
### 함수 arguments 속성
arguments는 객체이며, 배열 메서드를 사용할 수 없다.
arguments를 수정하려 하지 말 것
  ```
  function a() {
    console.log(arguments);
  }
  a(1, 2, 3);

  -> {'0':1, '1':2, '2':3}
  ```
### arrow function
  ```
  // 예제 1
  function getName(name) {
    return "Kim" + name;
  }

  // 예제 2
  var getName = (name) => "Kim" + name;

  -> 예제1과 예제2는 같다!
  ```

## 2. WEB UI 개발 - FE
### window객체
전역객체이며 생략가능하다
### 비동기처리, 콜백함수
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

HTML은 Tree태로 저장됨
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
  
## 3. JSP - BE

## 4. redirect & forward - BE

## 5. scope - BE

## 6. JSTL & EL - BE

## 7. MySQL - BE

## 8. SQL -BE

## 9. Maven - BE

## 10. JDBC - BE

## 11. WEB API - BE
