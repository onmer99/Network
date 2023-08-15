# 네트워크 개요(1)


### 네트워크는 뭐고, 인터넷은 뭐지?
- 네트워크
  - Net+work의 합성어로, 여러 장치들이 통신 기술을 통해서 서로 연결된 형태를 말한다
  - 장치들에는 휴대폰, 컴퓨터, 프린터 등등 다양한 물리적인 장치가 될 수 있다
  - 규모에 따라 PAN, LAN, MAN, WAN 등 다양한 네트워크가 존재한다
 
- 인터넷
  - Inter + network의 합성어로, 네트워크와 네트워크가 연결된 형태를 말한다  
    즉, 수 많은 장치들이 연결된 네트워크를 의미
    

<br/>  
  
### 인터넷은 무엇으로 구성되어 있을까?
- Hardware 구성요소
  - 장치
    - 라우터(router), 스위치(switch) :<br/>
      Host-To-Host에서 정보를 어떠한 방식으로 전달할 것인지를 결정하는 역할
    - 리피터(repeater) : 재반복을 통해 신호를 멀리 보내주는 역할
  - 링크
    - 유선 : 구리, 광케이블 등을 사용한 통신 방법
    - 무선 : Radio Frequency, 위성 전화 등의 통신 방법


- Software 구성요소
  - OS(운영체제) :<br/>
    사용자가 App, 컴퓨터를 편리하고 효율적으로 사용하게끔 도와주는 소프트웨어<br/>
    ex) Windows, Linux, Android, Ios, ...
  - 응용 프로그램 :<br/>
    Application 혹은 컴퓨터 프로그램을 말함
    ex) Web browser, 메신저 프로그램, ...
  - Protocol : <br/>
    프로그램들이 통신하기 위해 반드시 지켜야되는 약속, 규칙을 말함
    
  

### 네트워크 프로토콜이란?
- 프로토콜의 개념
  - 네트워크 프로토콜은 컴퓨터의 공통 언어라 생각하면 된다.<br/>
    ex) 세계 공용어인 영어처럼..
  - 네트워크로 연결된 장치들은, 서로 다른 소프트웨어와 하드웨어를 사용할 수 있다.<br/>
    이때 프로토콜은 각 장치들이 주고받는 메시지의 양식과 규칙을 정해놓은 것이기 때문에, 이를 통해 서로 통신을 할 수 있는 것이다.

<br/>

- 프로토콜의 기본 요소
  - 구문(Syntax) : 데이터의 형식(format), 부호화(coding), 신호 레벨(signal level)등을 규정<br/>
                사람 언어의 문법이라 생각하면 됨
  - 의미(Semantics) : 효율적이고 정확한 정보 전송을 위한 '협조 사항', 오류관리를 위한 '제어 정보'를 규정<br/>
                데이터의 각 부분이 무엇을 뜻하는지를 알 수 있게 정해둔 규칙이라 생각하면 됨
  - 시간(Timing) : 두 장치간의 통신 속도, 메시지의 순서 제어 등을 규정<br/>
                어떤 데이터를 얼마나 빠르게, 어떤 순서로 보낼지를 정한다 생각하면 됨                

<br/>

- 프로토콜의 종류
  - 네트워크 7계층에서, 각 계층별로 다르게 존재함
  - 응용(Application) : HTTP, SMTP, FTP, Telnet
  - 표현(Presentation) : ASCII, JPEG, MPEG, MIDI
  - 세션(Session) : NetBIOS, SAP, SDP, NWLink
  - 전송(Transport) : TCP, UDP, SPX
  - 네트워크(Network) : IP, IPX
  - 데이터 링크(Data Link) : Ethernet, Token Ring, FDDI, Apple Talk
  - 물리(Physical) : X

<br/>

- 프로토콜의 기능
  - 단편화(Fragmentation)와 재조립(Assembly)
    - 단편화 : 데이터를 쉽게 보내기 위해서 크기가 같은 작은 블록으로 나누어서 전송하는것
    - 재조립 : 데이터를 받을때, 나누어진 데이터 블록을 재합성하여 원래 메시지로 복원하는 기능

  - 캡슐화(Encapsulation)
    - 각 계층별 프로토콜에 적합한 데이터 블록을 만들기 위해서, 데이터에 정보를 추가하는 기능
    - 다음 계층으로 데이터를 보내기 전에, 출발지와 목적지 주소정보, 제어 정보, 오류 검출 부호 등 알맞은 정보를 부착한다

  - 연결 제어(Connection Control)
    - 통신시에 연결 지향성에 따라 연결 지향형과 비연결지향형 전송으로 나뉘는데, 각 전송방식을 위한 통로를 개설,유지,종결 하는 기능을 한다

  - 흐름 제어(Flow Control)
    - 데이터 양과 통신 속도 등이, 수신 측에서 받아낼 수 있는 한도를 초과하지 않도록 조정하는 기능

  - 오류 제어(Error Control)
    - 데이터 전송중 발생할 수 있는 오류나 착오 등을 검출하고 정정하는 기능

  - 순서 제어(Sequencing)
    - 연결지향형에만 사용되며, 데이터의 전달, 흐름, 오류 제어등을 위해서 순서를 지정한다
    - 순서가 정해진 데이터를 상대에게 보내면, 순서에 맞게 재조립하고 잘못된 정보는 재전송을 요구한다

  - 주소 설정
    - 출발지와 목적지 등의 주소를 설정하여 데이터를 정확하게 전달하는 기능을 한다

  - 동기화(Synchronization)
    - 통신하는 두 개체의 상태(시작, 종류, 검사)등을 일치시키는 기능

  - 다중화(Multiplexing)
    - 하나의 통신로를 여러개로 나누거나, 여러 개를 하나로 변환시켜서 다수의 사용자가 한번에 사용할 수 있도록 하는 기능

  - 전송 서비스(Transmission Service)
    - 통신하는 객체를 사용하기 쉽도록 별도의 추가 서비스(패리티 검사, 보안 요구, 서비스 등급, 우선순위 결정)를 제공하는 기능
    


### Network Edge와 Network Core가 뭐야?
- Network Edge : <br/>
  사용자들이 직접 접하게 되는 말단 부분으로, host(server와 client)가 속한다.<br/>
  또한 host들을 실제로 연결해주는 Access Network가 존재한다
  - Server : 대용량 data 처리 기능을 갖춘 PC
  - Client : 일반 사용자
  - Access Network : Host에서 Edge Router까지의 network를 말한다

<br>

- Network Core :<br/>
  출발지부터 목적지까지 데이터를 전송하는 장치들을 말한다.<br/>
  전달 방식에 따라서 회선 교환(Circuit Switching)과 패킷 교환(Packet Switching)으로 나뉜다.
  
  <br>
  
  - Circuit Switching
    - 전달경로와, 경로당 할당되는 자원(할당된 채널이나 시간 등)을 미리 정해놓는 방식이다.
    - 즉, 아무런 data가 전송되지 않아서 자원이 남더라도 다른곳에 쓰지 못한다
    - 자원 할당 방식에 따라서 FDM/TDM으로 나뉜다.<br/>
      - FDM(Frequency Division Multiflex, 주파수 분할 다중 전송 방식)<br/>
        : 주파수별로 유저를 할당
      - TDM(Time Division Multiflex, 시간 분할 다중 전송 방식)<br/>
        : 시간별로 유저를 할당<br>
        
        ![image](https://github.com/spharos3rd-CatchYou/Network/assets/108791919/d46db49d-cfd6-4079-a01c-efd4af055f7d)


  - Packet Switching
    - 데이터가 한번에 전송되는 것이 아니라, 여러 개의 패킷으로 나뉘어서 전송됨
    - 여러 source에서 하나의 router로 패킷들이 모이고, 설정된 양만큼 패킷이 모이면 목적지 router로 패킷이 전송되는 형태이다(store-and-forward 방식)
    - 패킷 교환이 store-and-forward 방식을 사용하는 이유
      - packet의 데이터가 다 완성이 되어야지 error 여부를 확인할 수 있다
      - packet의 헤더에 출발지와 목적지가 담겨있는데, 헤더는 가장 마지막에 라우터로 들어오기 때문이다
    - 하지만 router의 용량이 초과되면 packet 손실이 발생할 수 있다
    - 전송시간과 전체 전달 시간
      - 전송시간 T = L/R(s)<br>
       (L(bit):패킷사이즈, R(bps):링크의 시간당 전송능력)
      - 전체 지연 시간(전체 전달시간) End-to-End delay = hop count * T(s)<br>
      (hop: source부터 destination까지의 경로상에 존재하는 장치들, hot count: 경로상에 존재하는 hop의 수)
<br>

![image](https://github.com/spharos3rd-CatchYou/Network/assets/108791919/c6e55ae4-bb91-44ea-bbe7-33d179723892)

<br>

  - 서킷/패킷 스위칭 비교
    - 서킷 스위칭 -> 한 경로당 할당된 자원이 일정하게 유지되기에, 유저 입장에서 더 좋다
    - 패킷 스위칭 -> 더 많은 사용자를 수용할 수 있기에 공급자 입장에서 좋다


### 네트워크의 동작과정은?
- 사용자 -> Network Edge -> Access Network -> Edge Router -> Link -> 다음 Router -> Link -> 목적지 Edge Router -> 목적지

<br>
<br>
<br>
<br>

### 출처
  - https://computer-science-student.tistory.com/377
  - https://kdh0518.tistory.com/2 (내 블로그 ㅎㅎ)
  - https://jihwan4862.tistory.com/119
