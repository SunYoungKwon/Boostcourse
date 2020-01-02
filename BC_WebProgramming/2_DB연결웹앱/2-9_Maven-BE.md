# 웹 프로그래밍 2. DB 연결 웹 앱

## 9. Maven - BE

### Maven
- Java용 프로젝트 관리도구
- 프로젝트 빌드(build) 자동화
- 의존성 라이브러리 관리

### pom.xml
POM(Project Object Model)
```
<project>
  <modelVersion>POM Model 버전</modelVersion>
  <groupId>프로젝트를 생성하는 조직의 고유 아이디. 일반적으로 도메인을 거꾸로 씀</groupId>
  <artifactId>프로젝트에서 생성되는 기본 artifact의 고유 이름/artifactId>
  <version>프로젝트의 현재 버전. 개발중에는 뒤에 SNAPSHOT을 추가</version>
  <packaging>jar, war, ear 등</packaging>
  <name>프로젝트 이름</name>
  <description>프로젝트 설명</description>
  <url>프로젝트 URL</url>
	
  <dependencies>
    <dependency>
      <groupId></groupId>
      <artifactId></artifactId>
      <version></version>
      <scope>compile, runtime, provided, test</scope>
    </dependency>
  </dependencies>
 
  <build>빌드</build>
</project>
```

### CoC(Convention over Configration)
개발자가 내려야할 수 많은 결정들을 줄여주어, 단순성(Simplicity)을 확보하며, 유연성(Flexibility)을 잃어버리지 않도록 하기 위한 소프트웨어 디자인 패러다임  



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
