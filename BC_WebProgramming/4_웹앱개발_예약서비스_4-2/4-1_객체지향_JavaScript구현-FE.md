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



<br>

---

[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
