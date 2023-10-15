# HTTP란

- Hyper Text Transfer Protocol
  
  - 인터넷에서 정보를 주고 받기 위해 정해진 규칙

- 프로토콜이란...
  
  - 서로 다른 하드웨어간의 데이터 통신 규약

- HTTP의 특징으로는
  
  - Stateless(무상태성, 특정 상태를 유지하지 않는 것)
  
  - Connectionless(비연결성, 요청을 주고 받을 때만 연결 유지, 응답 후에는 통신하지 않음)이 있다.

# HTTP의 구조

- 클라이언트와 서버간의 통신에서 요청을 보내고 응답을 보낼 때, HTTP 메시지를 통해 통신이 이루어진다. 
  
  ![클라이언트 서버 체인](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview/client-server-chain.png)

- HTTP 메시지의 종류에는 HTTP Request/HTTP Response가 있다. 

- HTTP 메시지는 총 4개의 부분으로 나뉜다.
  
  ![](https://blog.kakaocdn.net/dn/4g6c8/btqJRmEIaA9/7eygSadanLoc5FmWCwGZPK/img.png)

## 

## HTTP Request 메시지

- 클라이언트와 서버간에 통신을 할 때, 클라이언트가 서버로 데이터 처리와 관련된 **요청**을 보내게 되는데 이 때 요청을 **HTTP Request**라고 한다.

![요청과 응답은 HTTP에서 공통 구조를 공유합니다](https://developer.mozilla.org/ko/docs/Web/HTTP/Messages/httpmsgstructure2.png)

### 1. Start Line

#### 서버가 특정 동작을 취할 수 있도록 요청을 알려주는 영역

```http
POST /post/11 HTTP/1.1
(Method) /(Path) (HTTP Version)
```

- HTTP Method: (Create, Read, Update, Delete)

- Request Target: URL, 프로토콜, 포트, 도메인의 절대 경로로 나타낼 수 있다. 요청을 보내는 경로(주소, 목적지)를 의미한다.
  
  - origin 형식: 경로 끝에 `?`를 붙이는 형식이다.
  
  - absolute 형식: 우리에게 익숙한 URL 형식
  
  - authority 형식: 도메인 이름이나 옵션 포트로 이루어진 URL 
  
  - asterisk 형식: `*` 로 서버 전체를 나타낸 형식

- HTTP Version: HTTP는 버전 별로 프로토콜이 다르기 때문에 HTTP Version을 Start Line에서 명시해준다.

### 2. Header

#### HTTP 메시지에 대한 정보를 명시한다. HTTP 요청에 대한 정보를 담고있다.

```http
Host: localhost:8000
User-Agent: Mozilla/5.0 (Macintosh;...) ... Firefox/51.0
Accept: text/html, application/xhtml+xml,...
Accept-Language: en-Us, en;q=0.6
Accept-Encoding: gzip, deflate
```

- Key-Value 값으로 정보를 나타낸다.

- Host: 요청이 전송되는 최종경로(목적지), target의 host url

- User-Agent: 요청을 보내는 클라이언트에 대한 정보(예시: 웹브라우저에 대한 정보), 해당 예시에서는 파이어폭스.

- Accept: 해당 요청이 받을 수 있는 파일 타입

### 3. Body

#### Request 중에 Body가 없는 경우도 많다.  실제 전송하는 데이터를 포함한다.

```html
<html>
...
</html>
```

Body는 두 가지 종류로 나뉜다.

1. 단일 리소스 본문(single-resource bodies): 헤더가 하나가 아닌 두 개로 정의된 하나의 단일 파일

2. 다중 리소스 본문(multiple-resource bodies): 본문이 여러개의 파트로 구성되어 있고 파트별로 다른 정보를 지니는 구조



## HTTP Response 메시지

### 1. Status Line

#### 클라이언트의 요청에 대한 서버의 응답 메시지

```http
HTTP/1.1 200 OK
(HTTP Version) (Response Message) (Status Text)

HTTP/1.1 404 NOT FOUND.
(HTTP Version) (Response Message) (Status Text)
```

- HTTP Version: HTTP는 버전 별로 프로토콜이 다르기 때문에 HTTP Version을 Start Line에서 명시해준다. 원활한 통신을 위해 요청과 같은 버전을 사용한다.

- Response Message: 클라이언트의 요청에 대한 결과를 나타내는 메시지. 요청이 잘 처리되었는지를 나타냄
  
  - `200`: 성공
  
  - `400`: 클라이언트 요청 오류
  
  - `500`: 서버 내부 오류

- Status Text: 결과에 대한 짧은 설명

### 2. Header

#### HTTP 메시지에 대한 정보를 명시한다. HTTP 요청에 대한 정보를 담고있다.

![HTTP_Response_Headers](https://i0.wp.com/hanamon.kr/wp-content/uploads/2021/09/HTTP_Response_Headers.png?resize=805%2C344&ssl=1)

- Header 값은 수백 개가 있다.

- Key-Value 값으로 데이터를 나타낸다.

- 임의의 Header 추가가 가능하다.

- 3가지 그룹으로 나눌 수 있다.
  
  - General headers: 메시지 전체에 적용되는 헤더(`Date`, `Cache-Control`, `Connection`)
  
  - Response headers: 응답에 대한 부가적인 정보를 갖는 헤더(`Access-Control-Allow-Origin`, `Allow`, `Content-Disposition`)
  
  - Entity headers: 컨텐츠의 길이와 같이 Entity Body에 대한 자세한 정보를 포함하는 헤더

### 3. Body

#### 응답 메시지는 Body를 항상 가진다.

```html
<html>
...
</html>
```

# HTTP와 TCP의 관계

- HTTP는 통신을 할 때 TCP 방식으로 HTTP 메시지를 주고 받는다.

- Application Layer(Layer 7)에 속하는 HTTP는 메시지 형식을 정의해주고, Transport Layer(Layer 4)에 속하는 TCP는 데이터가 전송되는 전송방식을 정의해준다.

# HTTPS란

![](http://blog.wishket.com/wp-content/uploads/2020/02/03-3.png)

- 기존의 HTTP에 Secure Socket이 추가된 프로토콜

- 데이터 암호화를 활용하여 외부에서 데이터를 탈취해도 키가 없으면 복호화를 할 수 없다.



### 참고자료:

[[10분 테코톡] 헌치, 써머의 HTTP - YouTube](https://www.youtube.com/watch?v=IjxkKQvn8Bc&ab_channel=%EC%9A%B0%EC%95%84%ED%95%9C%ED%85%8C%ED%81%AC)

https://www.zerocho.com/category/HTTP/post/5b344f3af94472001b17f2da

[HTTP 개요 - HTTP | MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Overview)

[[네트워크/HTTP] HTTP 메세지(message) - 요청과 응답 구조 - 하나몬](https://hanamon.kr/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-http-%EB%A9%94%EC%84%B8%EC%A7%80-message-%EC%9A%94%EC%B2%AD%EA%B3%BC-%EC%9D%91%EB%8B%B5-%EA%B5%AC%EC%A1%B0/)

[HTTP Request / Response 메시지 구조 :: 나의 개발 일기](https://ohcodingdiary.tistory.com/5)

[HTTP Header 정리, 각 Http Header가 갖는 의미를 알아야 Http를 배운 것이다.](https://jeong-pro.tistory.com/181)

[[HTTP-Header] HTTP 헤더란? 그리고 Header의 종류](https://wonit.tistory.com/308)

[HTTPS란? (동작방식, 장단점) | EunJeong Kwak](https://rachel-kwak.github.io/2021/03/08/HTTPS.html)
