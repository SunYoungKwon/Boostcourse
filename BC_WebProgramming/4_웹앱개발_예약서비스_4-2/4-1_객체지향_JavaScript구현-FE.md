# 웹 프로그래밍 - 4. 웹 앱 개발:예약서비스 2/4

## 1. 객체지향 JavaScript구현 - FE

### 배열의 함수형 메소드

```javascript
var employee = [{name : "Kim", age : 28, position : "Programmer"},
                {name : "Lee", age : 35, position : "Designer"},
                {name : "Park", age : 40, position : "CEO"}];
```

#### forEach

```javascript
employee.forEach(function(v) {
    console.log(v.name, v.age, v.position);
});

// ES6 arrow function
employee.forEach(v => console.log(v.name, v.age, v.position));
```

#### map

```javascript
var aging = employee.map(function(v) {
    return v.age + 1;		// 나이 한 살 추가!
});
```

#### filter

```javascript
var filteredEmployee = employee.filter(function(v) {
    return v.age > 30;
});
```

#### immutable

원본 데이터 유지하고 새로운 배열만 확인하기

```javascript
var filteredEmployee = employee.filter(function(v) {
    return v.age > 30;
}).map(function(v) {
  var obj = {};
  obj.name = v.name;
  obj.age = v.age + "세";
  obj.position = obj.position;
  return obj;
});
```

#### reduce

배열의 모든 요소에 대해 지정된 콜백 함수 호출하여, 콜백 함수의 반환 값을 누적하여 반환

초기값은 선택사항

```javascript
var totalAge = employee.reduce(function(prevValue, employee) {return prevValue + employee.age;}, 0);

console.log(totalAge);
```



### 객체리터럴

```javascript
// 객체 리터럴로 객체 만들기
var todo = {
    todos:["자바스크립트 공부하기"],
    addTodo: function(newTodo) {
       this.todos.push(newTodo);
    }, 
    showTodos: function() {
        this.todos.forEach(v => console.log(v));
    }
};
```



### this

> JavaScript에서 전역 스크립트나 함수가 실행될 때 실행문맥(Excution Context)이 생성된다. (실제 실행은 브라우저 내의 stack에 올라가서 실행됨)  모든 context에는 참조하고 있는 객체(thidBinding)가 존재하며, 이를 알기위새 this를 사용할 수 있다.

- 객체 내에서 **this**는 그 객체 자신을 가리킴
- **bind()**, **call()**, **apply()**를 사용하면 달라질 수 있음
- (참고) ES6에서 객체 내 메서드에 'function'키워드 생략 가능

```javascript
function getThis() {
    return this;
}

getThis();		// Window
new getThis();	// getThis{} -> Object
```

#### [call()](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Function/call)

- apply()와 유사하나 call()은 **인수 목록**을 apply()는 **인수 배열 하나**를 받는다.

```javascript
var hi = {
    todos: ["Hi!", "Hello!"]
};

todo.showTodos.call(hi);	// todo의 showTodos메소드를 hi를 참조하여 실행

> Hi!
  Hello!
```



<br>

---

[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
