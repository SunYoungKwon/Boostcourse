# 웹 프로그래밍 - 3. 웹 앱 개발:예약서비스 1/4

## 11. Controller - BE

### @RestController

- Spring4에서 RestAPI, WebAPI 개발을 위해 등장
- 이전 버전의 @Controller와 @ResponseBody를 포함

### MessageConvertor

- 자바 객체와 HTTP요청 / 응답 바디를 변환하는 역할
  - 외부에서 전달받은 JSON메서드를 내부에서 사용할 수 있는 객체로 변환
  - 컨트롤러를 리턴한 객체가 클라이언트에게 JSON으로 변환하여 전달할 수 있게 함
- @EnableWebMvc가 기본 재공함(jackson 라이브러리가 있어야 사용가능)

### MessageConvertor 종류

|        MessageConvertor 종류         | 기능                                                         |
| :----------------------------------: | :----------------------------------------------------------- |
|    ByteArrayHttpMessageConvertor     | converts byte arrays                                         |
|      StringHttpMessageConvertor      | converts Strings                                             |
|     ResourceHttpMessageConvertor     | convert org.springframework.core.io.Resource for any type of octet stream |
|      SourceHttpMessageConvertor      | converts javax.xml.transform.Source                          |
|       FormHttpMessageConvertor       | converts from data to/from a MultiValueMap<String, String>   |
| Jaxb2RootElementHttpMessageConvertor | converts Java objects to/from XML(added only if JAXB2 is present on the classpath) |
| MappingJackson2HttpMessageConvertor  | converts JSON(added only if Jackson2 is present on the classpath) |
|  MappingJacksonHttpMessageConvertor  | converts JSON(added only if Jackson is present on the classpath) |
|     AtomFeedHttpMessageConvertor     | convert Atom feeds(added only if Rome is present on the classpath) |
|    RssChannelHttpMessageConvertor    | converts Rss feeds(added only if Rome is present on the classpath) |

<br>

---
[HOME](https://github.com/tunaep5/Boostcourse/blob/master/README.md)
