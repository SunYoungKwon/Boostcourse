# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 8. Spring JDBC - BE
JBDC 프로그래밍의 반복적인 개발요소를 대신 처리

### Spring JDBC 패키지
- org.springframework.jdbc.core
- org.springframework.jdbc.datasource
- org.springframework.jdbc.object
- org.springframework.jdbc.support

  #### jdbcTemplate
  - 리소스 생성, 해지를 처리하여 연결을 닫는 것을 잊어 발생하는 문제를 피하게 함
  - Statement생성과 실행
  - SQL조회, 업데이트, 저장 프로시저 호출, ResultSet 반복호출
  - JDBC예외를 org.springframework.dao에 정의된 일반적인 예외로 변환
  - [예제코드](https://www.edwith.org/boostcourse-web/lecture/20660/)

  #### jdbcTemplate외의 접근방법
  - NamedParameterJdbcTemplate: '?'대신 이름으로 바인딩
  - SimpleJdbcTemplate
  - SimpleJdbcInsert

### DTO(Data Transfer Object)
- 계층(컨트롤러 뷰, 비지니스, 퍼시스턴스)간 데이터 교환을 위한 Java Beans
- 일반적으로 로직을 가지고 있지 않은 순수한 데이터 객체
- 필드와 getter, setter를 가짐
- toStirng(), equals(), hashCode()등을 오버라이딩할 수 있음

### DAO(Data Access Object)
- 데이터 조회 및 조작을 전담
- 일반적으로 데이터베이스를 조작하는 기능을 전담

### ConnectionPool
- DB연결은 비용이 많이 듦
- 커넥션 풀은 미리 커넥션을 여러 개 맺고 커넥션이 필요하면 커넥션 풀을 빌려 사용 후 반납

### DataSource
- ConnectionPool 관리
- 커넥션을 얻고 반납하는 작업 수행



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
