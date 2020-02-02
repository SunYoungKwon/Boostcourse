# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 10. 레이어드 아키텍처(Layered Architecture) - BE

### 레이어드 아키텍쳐
+ Controller에서 중목되는 부분을 처리한다면 별도의 객체/메소드로 분리
+ Service 객체
	+ 업무와 관련된 부분
	+ 비지니스 로직(business Logic)을 수행하는 메소드를 가지는 객체
	+ 보통 하나의 비지니스 로직은 하나의 트랜잭션으로 동작

### 트랜잭션
1. 원자성(Atomicity)
	+ 전체가 성공 or 전체가 실패
	+ Rollback : 5개의 과정을 가지는 하나의 트랜잭션이 있을 경우 3번에서 오류나면 앞의 모든 작업을 복원
	+ Commit : 하나의 트랜잭션이 성공적으로 수행되면 정보를 반영
	+ 롤백하거나 커밋되면 하나의 트랜잭션 처리 완료
2. 일관성(Consistency)
	+ 트랜잭션이 진행되는 동안 데이터가 변경되어도 처음 트랜잭션을 진행하기 위해 참조한 데이터로 작업 진행
3. 독립성(Isolation)
	+ 둘 이상의 트랜잭션이 동시에 실행되고 있을 경우 서로의 연산에 끼어들 수 없음
	+ 특정 트랜잭션이 완료될때 까지 다른 트랜잭션이 특정 트랜잭션의 결과를 참조할 수 없음
4. 지속성(Durability)
	+ 트랜잭션이 성공적으로 완료되었을 경우 결과는 영구적으로 반영함

### JDBC프로그래밍에서 트랜잭션 처리
Connection객체의 setAutoCommit메소드에 false를 파라미터로 지정 후 입력, 수정, 삭제 SQL의 실행이 모두 성공했을 때 Connection객체의 commit() 메소드 실행

### Spring에서 트랜잭션 사용
+ @EnableTransactionManagement : Spring Java Config에서 트랜잭션을 활성화 할 때 사용
+ Java Config를 사용하면 PlaformTransactionManager 구현체를 모두 찾아서 그 중에 하나를 매핑해 사용
+ 특정 트랜잭션 메니저를 사용하려면 TransactionManagementConfigurer를 Java Config파일에서 구현하고 원하는 특정 트랜잭션 메니저를 리턴하거나 특정 트랜잭션 메니저 객체 생성 시 @Primary 애노터이션을 지정
+ Presentation Layer : Controller 객체 동작
+ Service Layer : Business 메소드 동작
+ Repository Layer : DB 연결
+ 재사용, 유지보수 측면을 고려하여 Presentation 부분과 나머지의 설정을 따로 분리하는 것이 좋음



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
