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



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
