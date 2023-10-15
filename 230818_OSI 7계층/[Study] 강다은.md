# OSI 7계층

복습: No
생성일시: 2023년 8월 18일 오후 12:26

## OSI 7계층

---

1. 응용 계층 ( Application Layer) 
    1. 기능 :  프로세스간의 통신을 담당하는 계층 
    2. 프로토콜 : HTTP , SMTP, FTP, TELNET ,SSH, SMMP, IGMP 
        1. HTTP : WWW의 통신 프로토콜 
        2. SMTP : 단순우편전달 프로토콜 
        3. FTP : 파일전송 프로토콜 
        4. TELNET + SSH : 보안접속 프로토콜 
        5. SMMP : 단순 망 관리  프로토콜 
        6. IGMP  : 인터넷 그룹 관리 프로토콜 
    3. 단위 : Data
    
2. 표현계층 ( Presentation Layer) 
    1. 기능 : 전송하는 데이터의 표현 방식을 결정
    2. 프로토콜 : JPEF, MPEG, GIF, ASCII 등
    3. 단위 : Data
    
3. 세션계층 (Session Layer)
    1. 기능 :  주 지점간의 프로세스 및 통신하는 호스트 간의 연결 유지
    2. 프로토콜 : API, Socket
    3. 단위 : Data
        
        
4. 전송 계층 (Transport Layer)
    1. 기능 : 데이터를 캡슐화 하여 전송하는 계층, 사용자 간의 데이터 신뢰성 제공 
    2. 프로토콜 : TCP, UDP SCTP
        1. TCP : 전송제어 프로토콜 
            - 흐름제어, 오류제어, 혼잡 제어 제공
        2. UDP : 사용자 데이터그램 프로토콜 
        3. SCTP : 스트림 제어 프로토콜 
    3. 단위 : TCP-Segment, UDP-datagram
    4. 장치 : 게이트 웨이
        
        
5. 네트워크 계층 (Network Layer)
    1. 기능 : 호스트 와 호스트 간 라우팅 을 담당하는 계층  (경로 설정) 
    2. 프로토콜 : IP , ICMP 
        1. IP : 인터넷 프로토콜 
        2. ICMP  : 인터넷 제어 메시지 프로토콜 
        3. DHCP : 동적호스팅 설정 프로토콜 
        4. ARP : 주소변환 프로토콜 
    3. 단위 : Packet
    4. 장치 : 라우터
        
        
6. 데이터링크 계층 (DataLink Layer)
    1. 기능 : 물리계층의 데이터의 오류(오류검출) 와 흐름(주소할당)을 제어하는 계층 (신뢰성 제공)
    2. 프로토콜 : 이더넷, HDLC, ADCCP, LLC,  ALOHA
    3. 단위 : Frame
    4. 장치 : 브릿지, 스위치 등
        
        
7. 물리 계층 (Physical Layer)
    1. 기능 :  데이터를 전기적 신호로 변환해주는 계층 
    2. 프로토콜 : 10BASE-T, 100BASE-TX, ISDN, wired, wireless, RS-232, DSL, Twinax
    3. 단위 : bit  ⇒ 전기적 신호 
    4. 장치 : 통신 케이블, 리피터, 허브 등 
    

참고 :데이터 링크계층과 전송계층의 차이 

- 데이터 링크 계층과 차이점
    
    ![https://naon.me/media/network62.JPG](https://naon.me/media/network62.JPG)
    
- 데이터 링크 계층은 **물리적으로 1:1 연결**된 호스트 사이의 전송. 직접 묶여있는 호스트-노드 또는 노드-노드 사이에서 오류 제어, 흐름 제어
- 전송 계층은 **논리적으로 1:1 연결**된 송신과 수신 호스트 사이의 전송. **End to End(종단간) 호스트**로, 양 끝에 있는 호스트 사이에서 오류 제어, 흐름 제어

## OSI 7계층 경로

---

송신 : host → 응용 → 표현 → 세션 → 전송 → 네트워크 → 데이터 링크 → 물리 (캡슐화)

수신 : host ← 응용 ← 표현 ← 세션 ← 전송 ← 네트워크 ← 데이터 링크 ← 물리 (역캡슐화) 

![Untitled](https://github.com/spharos3rd-CatchYou/Network/assets/87631575/3f1ac285-5199-43d8-a2ac-c5432ee91a9f)
