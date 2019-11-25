# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 3. Ajax - FE
- Ajax: Asynchronous JavaScript and XML)

### 비동기
- [비동기설명영상](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
- [비동기설명글](http://www.phpmind.com/blog/2017/05/synchronous-and-asynchronous/)

### Ajax응답처리
```
// JSON 파싱해서 데이터 불러오기
var req = new XMLHttpRequest();

req.addEventListener("load", function() {
  console.log(typeof this.responseTest);        // string
  var jsonObj = JSON.parse(this.responseText);
  console.log(typeof jsonObj);                  // object

  var result = jsonObj.value;
  var output = document.querySelector(".output");         // 문서내에서 class="output"인 첫 번째 Element
  output.innerHTML += ("<span>" + result + "</span>");    // result를 <span>에 넣어서 출력
  });

req.open("GET", ",json.txt");
req.send();
```

### cross domain 문제
- JavaScript는 동일근원정책(Same-Origin Policy, SOP)으로 서로 다른 도메인에 대한 요청을 보안상 제한함. 이로인해 생기는 이슈가 cross-domain 문제
- XHR통신은 보안상의 이유로 다른 도메인간의 요청이 불가능
- JSONP(JSON with Padding) : 클라인언트가 아닌 각기 다른 도메인에 상주하는 서버로 부터 데이터를 요청하기 위해 사용. 현재 가방 많이 사용됨. 상속 비보안 문제로 인해 CORS로 대체되고 있음.
```
$.ajax({
  url: url,
  dataType: 'jsonp',
  jsonCallback: "myCallback",
  success: callback
});

$.getJSON(url + "?callback=?", data, callback);
```
  [예시 출처](https://kingbbode.tistory.com/26)
- CORS : 양쪽 서버의 헤더에 서로 통신을 허용하는 도메인을 등록(표준)

### 크롬 개발자도구 디버깅
- 크롬 개발자도구 Network패널
- [크롬 개발자도구 가이드](https://developers.google.com/web/tools/chrome-devtools/?hl=ko)


---
[<<< DOM API활용 - FE](#)  
[>>> Web Animation - FE](#)
