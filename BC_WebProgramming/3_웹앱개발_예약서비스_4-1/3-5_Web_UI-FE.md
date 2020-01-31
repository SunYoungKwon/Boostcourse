# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 5. WEB UI - FE

###  파일구성

#### Javascript

- body 태그 닫히기 직전에 위치
- 내용이 적다면 한 페이지에 작성해고 괜찮음
- 내용이 많다면 의미에 맞게 파일 구분하기
- 파일이 많다면 배포시 하나로 merge하기도 함



#### CSS

- head 태그 안에 위치



### DOMContentLoaded vs load

#### DOMContentLoaded

- DOMTree 분석이 끝나면 발생
- document 이벤트

#### load

- 모든 자원들이 다 받아져 브라우저에 렌더링까지 끝나면 발생
- window 이벤트



### Event Delegation

리스트 내 각 이미지에 대하여 이벤트를 등록하고자 한다면?

```html
<ul>
    <li><img src="image/img1.png"></li>
    <li><img src="image/img2.png"></li>
    <li><img src="image/img3.png"></li>
</ul>
```

1. 반복문을 이용하여 이벤트 등록

   - 리스트가 많은 경우 각각의 이벤트를 기억해야 하므로 메모리 낭비
   - 동적으로 리스트가 추가되는 경우 처리 어려움

2. ul 태그에 이벤트 등록

   ```javascript
   ul.addEventListener("click", function(event) {
       console.log(event.currentTarget.tagName, event.target.tagName);
       
       var target = event.target;
       
       if(target.tagName === "IMG") {
           // 원하는 기능 작성
       }
   })
   ```

   - event.target를 이용하면 클릭된 지점을 알려줌
   - **Event Delegation** : 부모DOM에 이벤트 위임



### Event Bubbling / Capturing

#### Event Bubbling

- 이벤트 발생지점이 하위 엘리먼트여도 감싸고 있는 상위 엘리먼트까지 올라가며 이벤트리스너가 있는지 찾음

#### Event Capturing

```javascript
ele.addEventListener('click', eventFunction, {
    capture: true
});
```

- 이벤트 버블링과 반대로 상위 엘리먼트에서 하위 엘리먼트로 내려감

#### stopPropagation()

```javascript
function eventFunction(event) {
	event.stopPropagation();
}
```

- 해당 이벤트가 전파되는 것을 막음



### HTML Templating

데이터와 HTML을 섞어서 화면에 출력

```javascript
var data = {  title : "hello",
              content : "lorem dkfief",
              price : 2000
           };
var html = "<li><h4>{title}</h4><p>{content}</p><div>{price}</div></li>";

var resultHTML = html.replace("{title}", data.title)
    				 .replace("{content}", data.content)
    				 .replace("{price}", data.price);
```



#### HTML Template 보관

- 서버에서 file로 보관하고 Ajax로 요청해서 받아오기

- HTML코드안에 숨겨두기

  - script태그는 type이 javascript가 아니라면 렌더링하지 않고 무시함

  ```html
  <script id="list-template" type="text/template">
  	<li>
          <h4>{title}</h4>
      	<p>{content}</p>
      	<div>{price}</div>
  	</li>
  </script>
  
  <script>
  	var html = document.querySelector("list-template").innerHTML;
  </script>
  ```

- (참고) [Template Literals](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Template_literals)



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
