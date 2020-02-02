# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 8. SQL - BE
### SQL(Structured Query Language)
- DML(Data Manipulation Language)
   + INSERT
   + UPDATE
   + DELETE
   + SELECT
- DDL(Data Definition Language)
   + CREATE
   + DROP
   + ALTER : 이미 존재하는 테이블의 구조나 형식 변경
- DCL(Data Control Language) : 권한관리, 데이터보안, 무결성에 관여
   + GRANT : 사용자를 생성하고 권한을 부여
   + REVOKE : 사용자 권한 제거
```sql
grant all privileges on DB이름.* to 계정이름 @'%' identified by '비밀번호';
flush privileges;

mysql -h호스트명 -u계정이름 -p DB이름;

quit;

\c       // 쿼리문 적는 도중 취소하기
```

### 기본용어
- 테이블
- 열(Column) : 특정 타입 및 크기를 가짐
- 행(Row) : 레코드, PK에 의해 구분됨
- Field : 행과 열의 교차점, 데이터를 포함할 수 있으며 데이터가 없다면 NULL을 가짐

### DML
#### SELECT
- DISTINCT
- ORDER BY
   + ASC
   + DESC
- WHERE Column IN ()
- WHERE Column LIKE '%A_'
- concat() : 컬럼의 합성
- 함수
   ```sql
   UCASE('seoul')             -> 'SEOUL'     // 대문자로
   UPPER('seoul')             -> 'SEOUL'

   LCASE('SEOUL')             -> 'seoul'     // 소문자로
   LOWER('SEOUL')             -> 'seoul'

   LPAD('hi', 5, '?')         -> 'hi???'
   RPAD('hi', 5, '*')         -> '***hi'

   SUBSTRING('happy', 3, 2)   -> 'pp'        // 3번째 부터 2개

   TRIM(' hello ')            -> 'happy'
   LTRIM(' hello ')           -> 'hello '
   RTRIM(' hello ')           -> ' hello'

   ABS(-2)                    -> 2           // 절대값
   MOD(29, 9)                 -> 2           // 나머지
   GREATEST(1, 2, 3)          -> 3           // 가장 큰 값
   LEAST(1, 2, 3)             -> 1           // 가장 작은

   NOW()
   SYSDATE()
   ```
- CAST 형변
   ```sql
   CAST(expression AS type)
   ```
- 그룹함수
   ```sql
   COUNT()           // NULL이 아닌 row의 수
   COUNT(*)          // row의 수
   AVG()
   MIN()
   MAX()
   SUM()
   GROUP_CONCAT()    // 그룹의 값을 ','로 이은 문자 반환(구분자 변경 가능)
   VARIANCE()        // 분산
   STDDEV()          // 표준편
   ```
- GROUP BY  

#### INSERT
새로운 데이터 삽입
```sql
INSERT INTO TableName (Field1, Field2, ...)
VALUES (Value of Field1, Value of Field2, ...);
```

#### UPDATE
데이터 수정
```sql
UPDATE TableName
SET Field1 = Value1, Field2 = Value2, ...
WHERE 조건식;         // 필수는 아니지만 작성하지 않을 시 모든 컬럼이 수정됨
```

#### DELETE
데이터 삭제
```sql
DELETE
FROM TableName
WHERE 조건식;
```

### DDL(Data Definition Language)
#### [MySQL Datatype](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)

#### CREATE
```sql
CREATE TABLE TableName(
    FieldName1 DataType [NULL|NOT NULL] [AUTO_INCREMENT] [DEFAULT], 
    FieldName2 DataType [NULL|NOT NULL] [AUTO_INCREMENT] [DEFAULT],
    ...,
    PRIMARY KEY (FieldName)
);
```

#### ALTER

#### DROP



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
