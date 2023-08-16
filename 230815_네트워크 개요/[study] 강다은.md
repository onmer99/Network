# 네트워크 개요

복습: No
생성일시: 2023년 8월 16일 오전 8:08

인터넷 개념

- 인터넷(Internet)이란 여러 통신망을 하나로 연결한다는 의미의 ‘인터 네트워크(inter-network)’라는 말에서 시작되었으며, 이제는 전 세계 컴퓨터들을 하나로 연결하는 거대한 컴퓨터 통신망을 의미한다
- 인터넷은 클라이언트와 서버로 구성되며, TCP/IP라는 기본 프로토콜을 통해 제공되고 있다.
    
    ⇒ 수많은 클라이언트 컴퓨터와 서버 컴퓨터, 그리고 이들로 구성된 네트워크들의 집합체이다.
    

인터넷의 핵심 : 분산된 네트워크, 패킷 스위칭

- 인터넷은 중앙 집중화된 제어나 관리 없이 여러 개별 네트워크들이 연결되어 있는데, 이런 분산된 구조는 안정성과 확장성을 제공한다.
- 데이터를 작은 단위인 패킷으로 나누어 전송하고 목적지에서 재조립하여 전달하는 패킷 스위칭 방식을 사용하여 효율적인 데이터 전송이 가능하다.

인터넷 구성요소: 클라이언트, 서버, 라우터, 모뎀 등

- 클라이언트 : 정보를 요청
- 서버 : 정보를 제공
- 라우터 : 데이터를 전달
- 모뎀 : 디지털 신호 ↔ 아날로그 신호

네트워크 개념

- 여러 컴퓨터가 각각 클라이언트와 서버로써 서로 연결되어 구성된 망을 컴퓨터 네트워크(computer network)라고 한다.

네트워크 프로토콜

- 컴퓨터나 장치 사이의 통신 규칙과 형식을 정의하는 규약이다.
- 네트워크 프로토콜은 데이터의 포맷, 전송 속도, 오류 검출 등의 역할을 한다

네트워크 프로토콜의 종류 

- 프로세스 유형에 따라 다양한 프로토콜이 존재한다
- 프로토콜은 주로 OSI 7계층으로 구분을 한다
    
     
    

OSI 7

7 응용 계층(Application Layer)

- 전송단위 : Data
- 프로토콜 : HTTP, SMTP, SSH, FTP, Telnet, DNS, modbus, SIP, AFP, APPC, MAP
    
    

6 표현 계층(Presentation Layer)

- 전송단위 : Data
- 프로토콜 : ASCII, MPEG, JPEG, MIDI, EBCDIC, XDR, AFP, PAP
    
    

5 세션 계층(Session Layer)

- 전송단위 : Data
- 프로토콜 : NetBIOS, SAP, SDP, PIPO, SSL, TLS, NWLink, ASP, ADSP, ZIP, DLC
    
    

4 전송 계층(Transport Layer)

- 전송단위 : TCP-Segment, UDP-datagram
- 프로토콜 : TCP, UDP, SPX, SCTP, NetBEUI, RTP, ATP, NBP, AEP, OSPF
    
    

3 네트워크 계층(Network Layer)

- 전송단위 : Packet
- 프로토콜 : IP, IPX, IPsec, ICMP, ARP, NetBEUI, RIP, BGP, DDP, PLP
    
    

2 데이터링크 계층(DataLink Layer)

- 전송단위 : Frame
- 프로토콜 : Ethernet, Token Ring, AppleTalk, PPP, ATM, MAC, HDLC, FDDI, LLC, ALOHA
    
    

1 물리 계층(Physical Layer)

- 전송단위 : Bit
- 프로토콜 : 10BASE-T, 100BASE-TX, ISDN, wired, wireless, RS-232, DSL, Twinax

네트워크 엣지  

개별 사용자나 기기들이 위치하는 부분  

네트워크 코어  

다양한 네트워크 요소들이 연결되어 있는 부분  

엣지와 코어의 연결   

엣지(client)  ↔ 코어(ISP) ↔ 엣지 (server)  
