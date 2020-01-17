# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 2. DOM API활용 - FE
### DOM 조작 API
- document.
- element.

### 유용한 DOM Element Object
```
<p><strong id="hi">Hello</strong>, World!</p>

<script>
  var a = document.getElementById("hi").tagName;          // "STRONG"
  var b = document.querySelector("strong").textContent;   // "Hello"
  var c = document.getElementById("hi").nodeType;         // 1
</script>
```
- tagName
- textContent
- nodeType(1: element, 2: attribute, 3: text, 8: comment)

### DOM 탐색 속성
- childNodes
- firstChild
- firstElementChild
- parentElement
- nextSibling
- nextElementSibling

### DOM 조작 메소드
- removeChild()
- appendChild()
- insertBefore()
- cloneNode()
- replaceChild()
- closest()

### HTML을 문자열로 처리
- innerText
- innerHTML
- [insertAdjacentHTML()](https://www.w3schools.com/jsref/met_node_insertadjacenthtml.asp)

<br>

### [DOM APIs 실습](https://www.edwith.org/boostcourse-web/lecture/20124/)

#### 실습1
```
var node = document.createElement("LI");
var textNode = document.createTextNode("melon");

node.appendChild(textNode);                 // <li>melon</li>

var list = document.querySelector("ul");
var strawberry = list.lastElementChild;     // <ul>의 마지막 <li>

strawberry.insertAdjacentElement("afterend", node);   // 해당 위치 뒤에 node 삽입

list.removeChild(strawberry.nextSibling);   // 삭제
```

#### 실습2
```
var node = document.createElement("LI");
var textNode = document.createTextNode("melon");

node.appendChild(textNode);                 // <li>melon</li>

var list = document.querySelector("ul");

list.insertBefore(node, list.childNodes[4]);   // 4번 자식노드 앞에 node 삽입
```

#### 실습3
```
var orange = document.querySelector("li:nth-child(2)");   // 두번째 <li>
orange.insertAdjacentHTML("afterend", "<li>melon</li>");   // 해당 위치 뒤에 node 삽입
```

#### 실습4
```
var list = document.querySelector("ul");
var apple = list.childNodes[1];
var strawberry = list.lastElementChild;

strawberry.insertAdjacentElement("beforebegin", apple);
```

#### 실습5
```
var reds = document.querySelectorAll(".red");
var parent = document.querySelector("ul");

for(var i = 0; i < reds.length; i++) {
  parent.removeChild(reds[i]);
}
```

#### 실습6
[Array.from](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/from)
[Element.closest()](https://developer.mozilla.org/en-US/docs/Web/API/Element/closest)
```
var blueNodes = document.querySelectorAll("section .blue");

Array.from(blueNodes).forEach(function(v) {
  var section = v.closest("section");
  var h2 = section.querySelector("h2");
  section.removeChild(h2);
});
```

### 폴리필(polyfill)
특정 기능이 지원되지 않는 브라우저를 위해 사용할 수 있는 코드 조각이나 플러그인




---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
