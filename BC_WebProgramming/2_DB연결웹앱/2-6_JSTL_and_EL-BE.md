# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 6. JSTL & EL - BE
- JSTL(JSP Standard Tag Library)
- EL(Expression Language)
- JSP에서 Java코드를 줄이기 위해 사용
- JSP는 결과를 출력하는데만 이용

### EL - 표현방법
```
${exp}
```
### EL - 기본객체
```
- pageContext
- pageScope
- requestScope
- sessionScope
- applicatinScope
- param              // request.getParameter
- paramValues        // request.getParameterValues
- header             // request.getHeader  
- headerValues       // request.getHeaders
- cookie             // request.getCookies
- initParam          // request.getInitParameter
```
### EL - 객체 접근 규칙
```
${'exp1'.'exp2'}
```
|exp1          |exp2       |result           |
|:------------:|:---------:|:---------------:|
|null          |?          |null             |
|?             |null       |null             |
|Map           |key        |key value        |
|List or Array |intValue   |List[intValue]   |
|List or Array |!intValue  |error            |
|Object        |name       |Object.getName() |
### EL - 연산자
#### 수치연산자
```
+
-
/     // div
*
%     // mod
```
- 객체는 자동으로 숫자로 변경
- 숫자로 변경할 수 없는 객체는 error
- null은 0으로 처리
#### 비교연산자
```
==    // eq
!=    // ne
<     // lt
>     // gt
<=    // le
=>    // ge
```
#### 논리연산자
```
&&    // and
||    // or
!     // not
```
#### empty연산자
```
${empty 'value'}
```
true를 반환하는 경우
- null
- 빈 문자열 ""
- 길이가 0인 배열
- 빈 Map
- 빈 Collection
#### 비교선택연산자
```
${(수식) ? trueValue : falseValue}
```
### EL 비활성화 하기
```
<%@ page isELIgnored = "true" %>
```


### JSTL - 환경설정
1. JSTL이용을 위한 라리브러리를 'WebContent/WEB-INF/lib/'에 추가하기 [라이브러리 다운로드](http://tomcat.apache.org/download-taglibs.cgi)
2. JSP파일에 아래 코드 추가
```
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```
### JSTL - 코어태그
#### 변수지원
- set
- remove
```
<c:set var="name" scope="사용할 scope" value="value" />
<c:remove var="name" scope="사용한 scope" />

<c:set target="${some}" property="propertyName" value="value" />
* some이 자바빈 : some.setPropertyName(value);
* some이 맵(map) : some.put(propertyName, value);
* Naming Convention을 지킬 것!
```
#### 흐름제어
- if(else는 없음)
```
<c:if test="조건">
   ...
</c:if>

* 조건은 주로 EL태그로 쓰임
```
- choose
```
<c:choose>
   <c:when test="조건1">
      ...
   </c:when>
   <c:when test="조건2">
      ...
   </c:when>
   <c:otherwise>
      ...
   </c:otherwise>
</c:choose>
```
- forEach
```
<c:forEach var="var" items="collection" [begin="beginNum"] [end="endNum"]>
   ...
</c:forEach>

* var는 해당 번째의 collecrion의 값을 저장할 변수
```
- forTokens
- import
```
<c:import url="URL" charEncoding="" var="" scope="">
   <c:param name="" value="" />
   ...
</c:import>

* charEncoding은 필수가 아님
* var은 읽어온 값을 가리킬 변수
* scope의 기본값은 page
* <c:param>은 url에 연결할 때 전송할 파라미터를 입력. 필수X
```
- redirect
```
<c:redirect url="URL">
   <c:param name="" value="" />
   ...
</c:redirect>

* <c:param>은 redirect할 때, 페이지에 전달할 파라미터 지정. 필수X
```
- url
#### 기타태그
- catch
- out
```
<c:out value="" escapeXml="{true|false}" default="defaultValue" />

* value는 JSPWriter에 출력할 값
* excapeXml은 태그를 문자로 인식하게 함. 기본값은 true
* default는 value가 존재하지 않을 때 사용될 값
```


---
[>>> 7. MySQL - BE](https://github.com/tunaep5/Boostcourse/blob/master/BC_WebProgramming/2_DB%EC%97%B0%EA%B2%B0%EC%9B%B9%EC%95%B1/2-7_MySQL-BE.md)
