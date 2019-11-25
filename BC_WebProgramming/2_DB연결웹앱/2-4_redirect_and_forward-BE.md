# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 4. redirect & forward - BE

### redirect
- 서버가 request를 보낸 클라이언트에게 특정 url로 이동하라고 response를 보내는 것  
- 과정 : server가 상태코드 302와 함께 Location Header에 담아 전송 -> client는 상태값이 302면 Location Header값으로 재요청 -> 브라우저 주소창이 전송받은 url로 변경
- 클라이언트는 2번의 request를 보냄
```
response.sendRedirect("url");
```
### forward
- 클라이언트가 보낸 request가 내부적으로 옮겨지는 것
- 과정 : client가 servlet1에 request보냄 -> servlet1의 결과를 HttpServletRequest에 저장하여 servlet2에 전송(forward) -> servlet2가 처리한 결과를 HttpServletResponse로 client에게 전달
- 클라이언트는 1번의 request를 보냄
- url의 변화가 없음
```
// servlet1의 'service' method
request.setAttribute("name", value);               // forward할 값을 저장
RequestDispatcher rd = request.getRequestDiapatcher("/servlet2");
RequestDispatcher.forward(request, response);      // forward

// servlet2의 'service' method
request.getAttribute("name");                      // servlet1에서 넘어온 값을 가져옴

* forward는 앱 내에서만 가능
* getAttribute()는 Object타입을 반환
```
### servlet & jsp 연동
- servlet은 프로그램 로직 수행에 유리
- jsp는 결과 출력에 유리
- servlet에서 수행한 로직의 결과값을 jsp로 forward하여 출력
```
RequestDispatcher rd = request.getRequestDiapatcher("/result.jsp");
RequestDispatcher.forward(request, response);      // forward
```
### EL
- jsp내에서 사용하는 표기법
```
// java
<%
int result = (int)request.getAttribute("result");
%>
<%=result %>

// EL
${result}

* 위의 두 코드는 같은 동작을 함
```


---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
