# 웹 프로그래밍 - 2. DB 연결 웹 앱

## 11. WEB API - BE
- 다양한 클라이언트(웹, 안드로이드, iOS 등)에게 정보를 제공하는 방식을 일원화 시키기위한 대표정인 방법이 HTTP프로토콜로 API를 제공하는 것이다.
- REST API : HTTP프로토콜로 제공하는 API

### API(Application Programming Interface)
API는 응용 프로그램에서 사용할 수 있도록, 운영체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스
- [참고 - JAVA API](https://docs.oracle.com/javase/8/docs/api/)

### REST API(Representational State Transfer API)
- REST형식의 API
- 핵심 컨텐츠 및 기능을 외부 사이트에서 활용할 수 있도록 제공되는 인터페이스
- 매시업(Mashup) : REST API들을 조합한 어플리케션을 만드는 것

#### REST 구성
- 자원(Resource) - URI
- 행위(Verb) - HTTP Method(GET, POST, PUT, DELETE)
- 표현(Representations)

|Method    |역할                 |
|:--------:|:-------------------:|
|POST      |리소스를 생성         |
|GET       |리소스를 조회         |
|PUT       |리소스를 수정         |
|DELETE    |리소스를 삭제         |

#### [REST의 특징](https://meetup.toast.com/posts/92)
1. Client - Server
2. Stateless
3. Cache
4. Uniform Interface
   - 리소스가 URI로 식별되어야 함
   - 리소스를 생성, 수정, 추가하고자 할 때 HTTP메세지에 표현하여 전송해야 함
   - 메시지는 스스로를 설명할 수 있어야 함(Self-descriptive Message)
   - 애플리케이션의 상태는 Hyperlink를 이용해 전이되어야 함(HATEOAS: Hypermedia As The Engine Of Application State)
5. Layerd System
6. Code-on-Demand(Optional)

- REST의 모든 것을 제공하지 않으면 Web API 혹은 HTTP API(그냥 REST API라고 하기도 함)

### URI규칙
- 슬래시 구분자(/)는 계층을 나타낼 때 사용한다
- URI 마지막 문자에 슬래시 구분자(/)를 포함하지 않는다
- 가독성을 높이기 위해 하이픈(-)을 사용할 수 있다
- 언더바(_)는 사용하지 않는다
- URI경로는 소문자만 사용한다
- [RFC 3986](https://tools.ietf.org/html/rfc3986)(URI 문법 형식)은 URI스키마와 호스트를 제외하고는 대소문자를 구분한다
- 파일확장자는 URI에 포함하지 않는다
- Accept Header를 사용한다

### 상태코드

#### 성공
|상태코드   |                                    |
|:---------:|:----------------------------------:|
|200        |클라이언트의 요청을 정상적으로 수행    |
|201        |리소스 생성 요청에 성공(POST)         |

#### 클라이언트로 인한 오류
|상태코드   |                                    |
|:---------:|:----------------------------------:|
|400       |클라이언트의 요청이 부적절함            |
|401        |클라이언트가 인증되지 않은 상태에서 보호된 리소스를 요청</br>(예. 로그인 하지 않은 유저가 로그인해야 요청가능한 리소스를 요청했을 때)   |
|403        |유저 인증상태와 관계없이 응답하고 싶디 않은 리소스를 요청</br>(403은 리소스가 존재한다는 정보를 주기 때문에 권장하지 않음)|
|405        |클라이언트가 요청한 리소스에서 사용 불가한 Method를 이용함   |

#### 서버로 인한 오류
|상태코드   |                                    |
|:---------:|:----------------------------------:|
|301        |클라이언트가 요청한 리소스에 대한 URI가 변경되었을 때</br>(응답 시 Location header에 변경된 URI를 적어줘야 함)    |
|500        |서버에 문제가 있을 경우       |



<br>



---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)