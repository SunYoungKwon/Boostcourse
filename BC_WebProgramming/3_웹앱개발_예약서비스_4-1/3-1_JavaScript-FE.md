# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 1. JavaScript - FE

### [배열](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array)
```
var a = [];                              // 배열선언
var b = [1, "hello", null, true, []];    // 초기화와 함께 배열 선언
```
- 배열안에는 모든 타입(함수, 배열, 오브젝트 등...)이 다 들어갈 수 있다

#### 배열의 유용한 메서드들
```
console.log(a.length);  // 배열의 길이 출력

a.unshift(5);        // 맨 앞에 추가
a.push(5);           // 맨 뒤에 추가
a.shift();           // 첫 번쨰 항목 제거
a.pop();             // 마지막 항목 제거

[1, 2, 3].indexOf(3);         // 항목의 인덱스 반환, 없으면 -1
> 2

[1, 2, 3].join();             // 배열의 각 항목을 ','로 연결한 문자열 반환
> "1,2,3"

[1, 2, 3].concat(2, 3);       // 원래 배열은 변경되지 않는다
> [1, 2, 3, 2, 3]

a = [...b, 2, 3];             // a = b.concat[2, 3];과 같다

[1, 2, 3, 4, 5].slice(2);     // index 2 앞에서 자르기
> [3, 4, 5]

[1, 2, 3, 4, 5].slice(1, 3);  // index 1부터 index 3(미포함)까지
> [2, 3]
```

### 배열의 탐색

#### [forEach](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
```
var a = [1, 2, 3];

a.forEach(function(v, i, o) {
   console.log(v);
});

// a.forEach(v => console.log(v));

> 1
  2
  3
```

#### [map](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- 각각의 요소에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열 반환
```
var origin = [1, 2, 3];

var mapped1 = origin.map(function(v) {
   return v * 2;
});

var mapped2 = origin.map(v => v * 2);

console.log(origin, mapped1, mapped2);

> [1, 2, 3] [2, 4, 6] [2, 4, 6]
```

#### [filter](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- 주어진 조건에 맞는 요소만 모아 새로운 배열로 반환
```
var origin = [3, 7, 2, 8, 6];

var result1 = origin.filter(function(v) {
   return v > 5;
});

var result2 = origin.filter(v => v > 5);

console.log(origin, result1, result2);

> [3, 7, 2, 8, 6] [7, 8, 6] [7, 8, 6]
```
</br>

### 객체
```
var obj = {key : "value"};    // 객체의 선언

console.log(obj.key);         // key에 해당하는 value 가져오기
> "vaule"

console.log(obj["key"]);      // key에 해당하는 value 가져오기
> "value"
```

### 객체의 탐색
#### for-in문
```
var obj = {name : "Kim", age : 20};

for(key in obj) {
   console.log(key);
}

> name
  age
```
#### keys
- 오브젝트의 key값을 배열로 반환
- forEach와 함께 많이 사용
```
var obj = {name : "Kim", age : 20};

console.log(Object.keys(obj));
> ['name', 'age']

Object.keys(obj).forEach(function(v) {
   console.log(obj[v]);
});
> "Kim"
  20
```



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
