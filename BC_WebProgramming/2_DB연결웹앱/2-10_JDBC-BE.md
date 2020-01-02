# 웹 프로그래밍 2. DB 연결 웹 앱

## 10. JDBC - BE

### JDBC(Java Database Connectivity)
자바를 이용한 데이터베이스 접속과 SQL문장의 실행과 실행 결과로 얻어진 데이터의 핸들링을 제공하는 방법과 절차에 대한 규약

#### JDBC 드라이버 설치
```
<dependency>
  <groupId>mysql</groupId>
  <artifactId>mysql-connector-java</artifactId>
  <version>5.1.45</version>
</dependency>
```

####  JDBC 사용
1. import java.sql.*;
2. 드라이버를 로드
3. Connection 객체 생성
4. Statement 객체를 생성 및 쿼리문 수행
5. SQL문에 결과물이 있다면 ResultSet 객체를 생성
6. 모든 객체를 close(열었던 순서 반대로 닫기)
* Connection, Statement는 인터페이스



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
