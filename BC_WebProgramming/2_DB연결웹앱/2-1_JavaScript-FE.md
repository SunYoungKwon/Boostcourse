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


---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
