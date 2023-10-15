# 웹사이트에 접속할 때 생기는 과정에 대해 설명

![](https://blog.kakaocdn.net/dn/bB27VM/btqInsHdO5P/p1x9GeFMhOc6b48Izwhdkk/img.png)

1. 브라우저는 `DNS서버`로 요청을 보내고 요청을 통해 입력한 URL(도메인)에 해당하는 IP주소를 받아온다.
   
   - 우리가 흔히 브라우저에 입력하는 `www.naver.com`과 같은 URL은 `도메인`이라고 불린다.
   
   - 실제 `IP주소`는 `1.81.00.001`과 같은 형식의 .과 숫자로 이루어진 외우기 힘든 주소이다.
   
   - IP주소는 외우기 힘들기 때문에 IP주소를 변환하여 만든 인터넷 주소가 `도메인`이다.

2- 브라우저는 서버에게 `HTTP 요청 메시지`를 보내며, 웹사이트의 사본 요청을 한다. 이 때, 클라이언트와 서버 사이의 모든 데이터는 `TCP/IP 연결`을 통해 전송된다.

3-  서버는 `HTTP 요청 메시지`를 받아서 해당 URL에 해당하는 데이터를 찾는다.

- 요청 메시지
  
  ![0404 img04](https://swimjiy.github.io/static/8a09e4775b60076a42f14a34daf61fb9/6ed10/0404_img04.png)

4- 찾은 데이터는 HTTP프로토콜을 이용하여 `HTTP 응답 메시지`가 생성되고, HTTP Body에 부분에 저장된다. 

- 응답 메시지
  
  ![0404 img05](https://swimjiy.github.io/static/32bcf42ae4ecfcccc4d807894a555da5/6ed10/0404_img05.png)

5- 서버는 찾은 데이터를 `TCP/IP 프로토콜`을 통해 클라이언트에게 보낸다.

6- 도착한 `HTTP 응답 메시지`는 HTTP 프로토콜을 통해 웹 페이지 데이터로 변환된다.

7- 브라우저는 변환된 웹 페이지 데이터를 사용자에게 보여준다.

# TCP와 UDP의 차이는?

## TCP란:

- TCP(Transmission Control Protocol)

- 서버와 클라이언트간에 데이터를 `신뢰성 있게` 전달하기 위해 만들어진 프로토콜이다.
  
  - 신뢰성이란: 데이터의 `유실이 없이` 전달되도록 하는 것

- 기존 IP만을 이용하여 데이터 전송을 할 때 발생할 수 있는 문제점을 보완한다.
  
  1. IP를 이용하여 데이터를 전송할 때, `패킷을 받는 대상의 연결 여부를 확인하지 않고` 보낸다.
  
  2. 순서가 있는 패킷을 여러개 전송했을 때, `데이터의 전송/수신의 순서를 보장하지 않는다.`
  
  3. 패킷을 가지고 있던 호스트가 강제 종료될 시, `패킷 또한 소실`되어 패킷이 목적지로 도달하지 못한다.

. 해당 문제점들을 방지하기 위해서 TCP는 다음과 같은 기능을 제공한다.

1. 패킷을 받을 노드가 서비스 가능한 상태인지 확인/노드와의 연결 수립
   
   - `TCP 3 Way HandShake`를 통해 노드와 통신을 수행한다.
     
     ![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FNHdDC%2Fbtq4qzFhnaG%2FpVZVWLM8S7ROCZvhaaiBDk%2Fimg.png)

2. 전송을 제어하는 정보를 패킷에 추가
   
   - 전송 제어 규약에 대한 정보를 패킷에 추가한다(Port 정보, 순서 정보).
   
   - `Port 정보`: 패킷이 어떤 프로세스에 전달되어야 하는지를 명시해놓은 정보
   
   - `순서 정보`: 전달할 패킷이 여러개일 때, 패킷의 처리 순서를 명시해놓은 정보
- 두 가지 정보를 통해 패킷이 어떤 프로세스에게, 어떤 순서로 전송되어야 할지를 알 수 있다.

## UDP란:

- UDP(User Diagram Protocol)

- TCP와 반대로 `비연결형`이며, `신뢰성이 없는` 전송 프로토콜이다.

- 비연결형이며, 신뢰성이 없기 때문에 TCP와 반대로 TCP에서 패킷의 유실을 막기 위해 사용하는 TCP 3 Way HandShake를 사용하지 않는다.

- `흐름제어`, `오류제어`를 하지 않고, 손실된 패킷에 대한 `재전송을 하지 않기 때문에` 비교적 데이터 `전송이 빠르다`는 장점이 있다.

- 데이터 유실/에러 탐지를 위해 `checksum`을 사용한다.
  
  ![UDP segment header](https://blog.kakaocdn.net/dn/3oJdT/btrbljO4lET/mq8qkOivmkGrL2jsLyMLeK/img.png)
  
  - 도착 IP주소, 송신/수신 포트번호, 데이터 길이, payload 등의 데이터를 32비트 단위로 쪼개서 모두 더한 값을 계산과정을 거쳐 `checksum`값을 구한다.
  
  - 송신측에서는 checksum값을 값을 같이 보내고, 수신측에서는 받은 데이터를 활용하여 checksum값을 산출해낸다.
  
  - 수신과 송신 측 checksum 값이 `같다면 데이터 유실/에러 없이 전송`이 이루어진 것이고, `아니라면 유실/에러가 발생`한 것이다.

## 참고자료

https://xn--3e0bx5euxnjje69i70af08bea817g.xn--3e0b707e/jsp/resources/domainInfo/domainInfo.jsp

[웹의 동작 방식 - Web 개발 학습하기 | MDN](https://developer.mozilla.org/ko/docs/Learn/Getting_started_with_the_web/How_the_Web_works)

https://velog.io/@ylyl/TIL-web-operations

[웹(WWW)의 동작 원리](https://all-young.tistory.com/21)

[Switch to dark mode](https://swimjiy.github.io/2020-04-04-web-http)

[3-2. 전송(Transport) 계층: 신뢰성 있는 데이터 전송(RDT)](https://dev-nicitis.tistory.com/27)

[[인터넷 프로토콜] TCP란 무엇인가? 패킷 전송을 위한 정보의 관점에서 보는 TCP(Transmission Control Protocol) — 조세영의 Kotlin World](https://kotlinworld.com/94)

https://limjunho.github.io/2021/06/05/UDP-cksum.html (checksum관련 자료)
