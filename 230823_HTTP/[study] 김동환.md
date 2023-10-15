# HTTP

### HTTP란 무엇인가?
- HyperText Transfer Protocol<br>
  : `웹`에서 Client와 Server가 통신할때 사용하는 `메시지의 구조 및 교환 방법`을 정의한 프로토콜이다. <br>
   스프링 Docs처럼 웹에서 통신할때는 HTTP를 따라해야 통신할 수 있다고 생각하면 될듯! 



### HTTP 메시지의 종류와 구조는 어떻게 될까?
- HTTP `요청 메시지`<br>
![request-message](https://github.com/spharos3rd-CatchYou/Network/assets/108791919/aacd1d17-c983-4377-bc31-1278836c7ed9)
<br>

  `요청라인`, `헤더라인`, `공백라인`, `개체몸체`로 구성되어있다<br><br>
ex) <br>
　　　(요청라인)<br>
GET /hello.htm HTTP/1.1 <br>
　　　(헤더라인)<br>
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) <br>
Host: www.tutorialspoint.com<br>
Accept-Language: en-us<br>
Connection: close<br>
　　　(공백라인)<br>
　　　(개체몸체)<br>
Body..
<br>


    1. 요청라인
        - Method : GET, POST, HEAD, PUT, DELETE, CONNECT, OPTIONS, TRACE 등의 방법이 존재
        　　(HEAD -> GET과 유사, HEAD 요청에 의한 Response는 객체 없이 Http 메시지만 돌아옴)
        - Version : HTTP의 버전
    2. 헤더라인
        - Host : 웹 프록시 캐시에서 필요한 정보
        - Connection : 지속 연결 사용을 결정
        - User-agent : Server에게 요청을 보내는 브라우저의 타입을 명시
        - Accept-language : 응답받을 언어 버전을 의미. 서버에 존재해야함
       　　기타등등..
    3. 개체몸체
        - Get에서는 비어있고, Post에서 사용됨


<br>

- HTTP `응답 메시지`
![response-message](https://github.com/spharos3rd-CatchYou/Network/assets/108791919/1ea9ae96-51b6-4be7-87e7-0c530242625c)

`상태라인`, `헤더라인`, `공백라인`, `개체몸체`로 구성되어있다<br>
<br>
ex)<br>
　　　(상태라인)<br>
HTTP/1.1 200 OK<br>
　　　(헤더라인)<br>
Date: Mon, 27 Jul 2009 12:28:53 GMT<br>
Server: Apache/2.2.14 (Win32)<br>
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT<br>
Content-Length: 88<br>
Content-Type: text/html<br>
Connection: close<br>
　　　(공백라인)<br>
　　　(개체몸체)<br>
Body...<br>
<br>

    1. 상태라인
        - status : 200, 400, 404, 500 등등..<br>
        　　　　　1xx(정보) : 요청을 받았으며 프로세스를 계속 진행합니다.<br>
        　　　　　2xx(성공) : 요청을 성공적으로 받았으며 인식했고 수용하였습니다.<br>
        　　　　　3xx(리다이렉션) : 요청 완료를 위해 추가 작업 조치가 필요합니다.<br>
        　　　　　4xx(클라이언트 오류) : 요청의 문법이 잘못되었거나 요청을 처리할 수 없습니다.<br>
       　　　　　 5xx(서버 오류) : 서버가 명백히 유효한 요청에 대한 충족을 실패했습니다.<br>
        - phrase : 상태코드 연관문장으로 OK, Bad Request, Not Found 등등<br>
    2. 헤더라인
        - Connection : Client에게 메시지를 보낸 후 TCP 연결을 어떻게 할지 정함
        - Date : Response를 보낸 날짜와 시간을 나타냄
        - Server : 메시지가 어떤 서버에 의해 만들어졌는지를 나타냄<br>
        　　　　Request 메시지의 User-agent와 비슷함
        - Last-Modified : 객체가 생성되거나 마지막으로 수정된 날짜와 시간을 나타낸다<br>
        이 헤더는 로컬 클라이언트와 네트워크 캐시서버(프록시 서버)에서의 객체 캐싱에 매우 중요하다
        - Content-Length : 객체의 바이트 수
        - Content-Type : Body 내부의 객체의 타입을 나타낸다
<br>
<br>

### HTTP와 TCP의 관계
- HTTP가 웹 상에서 주고받는 `메시지의 구조 및 교환 방법`을 정해주고, TCP가 실제 데이터 패킷들의 전송에서 `정확성과 순서를 보장하여 전달하는 기능`을 담당한다

<br>

### HTTPS와의 관계는 어떻게 될까?
- HTTPS는 HyperText Transfer Protocol Secure의 줄임말로, HTTP를 `SSL/TLS 인증서를 사용하여 주고받는 데이터를 암호화`한 프로토콜이다.
- 두 개의 차이는 사용하는 `포트`, `데이터 전송 속도`, `검색 엔진 최적화`, `보안성`등이 있다.
