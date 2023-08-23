1. **HTTP란 무엇인가?**
   - HTTP (Hypertext Transfer Protocol)는 인터넷에서 웹 페이지와 관련된 리소스를 전송하기 위해 사용되는 통신 프로토콜입니다. 웹 브라우저와 웹 서버 간의 상호작용에 주로 사용됩니다.

2. **HTTP의 구조**
   - HTTP는 클라이언트-서버 모델에 기반하며, 클라이언트(대개 웹 브라우저)가 서버에 요청을 보내면 서버가 해당 요청에 응답합니다.
   - 요청과 응답은 HTTP 메시지로 구성되며, 이 메시지는 시작줄, 헤더, 빈 줄, 그리고 선택적인 본문으로 이루어져 있습니다.

- HTTP 요청 예시
```
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: keep-alive
```

GET: 사용된 HTTP 메서드입니다.  
/index.html: 웹 서버에 요청되는 리소스의 경로입니다.  
Host, User-Agent, Accept 등: HTTP 헤더들이며, 요청에 대한 추가적인 정보를 제공합니다.  


- HTTP 응답 예시
```
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2020 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Sun, 26 Jul 2020 20:56:15 GMT
Content-Length: 88
Content-Type: text/html
Connection: Closed

<html>
	<head>
		<title>An Example Page</title>
	</head>
	<body>
		Hello World!
	</body>
</html>
```

HTTP/1.1 200 OK: HTTP 버전과 상태 코드 및 상태 메시지입니다.  
Date, Server, Content-Length 등: HTTP 헤더들이며, 응답에 대한 추가적인 정보를 제공합니다.  
<html>...</html>: HTML 본문이며, 브라우저가 해석하고 사용자에게 보여줄 내용입니다.  


3. **HTTP와 TCP의 관계?**
   - HTTP는 응용 계층의 프로토콜이며, 실제 데이터 전송을 처리하는 것은 전송 계층의 TCP (Transmission Control Protocol)입니다. 즉, HTTP는 데이터의 형식과 메시지 교환 방법을 정의하고, TCP는 데이터를 신뢰성 있게 전송합니다.
   - HTTP 요청과 응답은 TCP 연결 위에서 이루어집니다. 클라이언트가 웹 서버에 연결을 요청하면 TCP 연결이 생성되고, 이 연결 위에서 HTTP 메시지가 교환됩니다.

<detals>
	<summary>- 정의</summary>
- TCP (Transmission Control Protocol):
연결 지향적 프로토콜로, 데이터 전송을 위한 신뢰성 있는 연결을 제공합니다.
데이터는 패킷 단위로 분할되어 전송되며, 수신 측에서는 이 패킷들을 원래의 순서대로 재조립합니다.
데이터가 손실되거나 오류가 발생하면, TCP는 재전송을 통해 데이터의 정확한 전송을 보장합니다.

- HTTP (HyperText Transfer Protocol):
웹에서 사용되는 프로토콜로, 클라이언트와 서버 간의 요청 및 응답을 정의합니다.
HTTP는 TCP 위에서 동작하여, TCP의 신뢰성 있는 전송 메커니즘을 활용합니다.
</details>

<details>
	<summary>- 예시</summary>
웹 브라우저에서 "http://www.example.com"에 접속하려고 할 때 발생하는 과정:

1. **TCP 연결 설정**:
   - 웹 브라우저는 웹 서버의 IP 주소와 포트 80 (기본 HTTP 포트)을 대상으로 TCP 연결을 시작합니다.
   - 이 과정은 "3-way handshake"로 알려져 있습니다.
     1. 웹 브라우저 (클라이언트)가 서버에 SYN 패킷을 보냅니다.
     2. 서버는 SYN-ACK 패킷으로 응답합니다.
     3. 클라이언트는 ACK 패킷을 보내 연결을 확립합니다.

2. **HTTP 요청 및 응답**:
   - TCP 연결이 확립되면, 웹 브라우저는 해당 연결을 통해 HTTP 요청을 서버에 전송합니다.
```
GET / HTTP/1.1
Host: www.example.com
```
   - 서버는 요청을 처리한 후, 같은 TCP 연결을 통해 HTTP 응답을 보냅니다.
```
HTTP/1.1 200 OK
Content-Type: text/html

<html> ... 웹페이지의 내용 ... </html>

```

3. **TCP 연결 종료**:
   - 데이터 전송이 완료되면, TCP 연결은 일반적으로 종료됩니다.
   - 이 과정은 "4-way handshake"로 진행됩니다.
</details>

4. **HTTP의 메세지 종류는 어떻게 구성되고 어떤 역할을 하는지?**
   - HTTP 요청 메시지: 클라이언트가 서버에 특정 리소스를 요청할 때 사용됩니다. 요청 메서드 (GET, POST, PUT, DELETE 등)로 시작합니다.
   - HTTP 응답 메시지: 서버가 클라이언트의 요청에 대한 응답을 전송할 때 사용됩니다. 상태 코드(예: 200 OK, 404 Not Found)를 포함하여 요청에 대한 결과를 나타냅니다.
   - 각 메시지는 헤더를 포함하여 요청/응답의 메타데이터를 전달하며, 필요한 경우 본문을 포함하여 실제 데이터를 전송합니다.

5. **HTTPS와의 관계**
   - HTTPS는 HTTP의 보안 확장 버전입니다. HTTP는 텍스트 기반으로 데이터를 전송하므로 중간자가 트래픽을 가로채면 내용을 읽을 수 있습니다.
   - HTTPS는 SSL (Secure Sockets Layer) 또는 TLS (Transport Layer Security)를 사용하여 데이터를 암호화합니다. 이로 인해 중간자 공격 (Man-in-the-Middle Attack) 또는 데이터 가로채기와 같은 보안 위협으로부터 통신 내용을 보호합니다.
   - HTTPS를 사용하면 클라이언트와 서버 간의 모든 HTTP 통신이 암호화되어 안전하게 전송됩니다.


```
요청
[암호화된 메시지]
GET /secure-page HTTP/1.1
Host: www.secure-example.com
User-Agent: Mozilla/5.0
...
```
```
응답
[암호화된 메시지]
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2029 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
...
<html>
<body>
<h1>Secure Content!</h1>
</body>
</html>
```

