# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 5. scope - BE
### scope의 종류
1. Application : 어플리케이션이 만들어져서 소멸될 때 까지
2. Session : 세션이 만들어져서 소멸될 때까지(상태유지)
3. Request : 클라이언트가 요청을 보내고 서버가 응답할 때까지
4. Page : 선언된 페이지 내에서만 사용가능
### Page Scope
- PageContext 추상클래스 이용
- jsp는 pageContext라는 내장객체가 존재함
- forward 불가
- 지역변수와 쓰임이 유사하나 EL표기법으로 사용할 때 유용
```java
pageContext.setAttribute("name", value);
pageContext.getAttribute("name");
```
### Request Scope
- HttpServletRequest 객체를 이용
- JSP에서는 request 내장 객체를 이용
- forward시 값을 유지시키는 데 사용
```java
request.setAttribute("name", value);
request.getAttribute("name");
```
### Session Scope
- 웹 브라우저(클라이언트) 별로 변수를 관리하고자 할 때 이용
- HttpSession 인터페이스를 구현한 객체를 이용
- JSP에서는 session 내장 객체를 이용
- 웹 브라우저간의 탭들은 세션정보를 공유함
- 브라우저가 종료되면 사라짐
- 예) 로그인, 장바구니
```java
session.setAttribute("name", value);
session.getAttribute("name");
```
### Application Scope
- ServletContext 인터페이스를 구현한 객체를 이용
- JSP에서는 application 내장 객체를 이용
- 어플리케이션 당 하나 객체를 가짐
- 모든 클라이언트가 공통적으로 사용할 값을 저장
```jsp
/* ApplicaionScope01.java (servlet) */
ServletContext applicaion = getServletContext();
application.setAttribute("name", value);

/* ApplicationScope02.java (servlet) */
ServletContext applicaion = getServletContext();

try {
   int value = (int)application.getAttribute("name");    // 객체이기 때문에 형변환 필요
   // Do something
   application.setAttribute("name", value);     // 값을 다시 저장
} catch(NullPointerException e) {               // "name"이라는 객체가 존재하지 않는 경우
   // Error message
}

/* applicationScope01.jsp */
<%
try {
   int value = (int)application.getAttribute("name");
   // Do something
   application.setAttribute("name", value);     // 내장 객체 이용
} catch(NullPointerException e) {
   // Error message
}
%>
```



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)