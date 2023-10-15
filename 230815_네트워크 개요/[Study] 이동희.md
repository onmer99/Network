# 네트워크란 무엇인가?

- 네트워크란 두 대 이상의 컴퓨터가 정보, 자원 교환을 위해 공유하는 통신망이다. 

- 통신을 수행하기 위해 컴퓨터들은 반드시 네트워크에 연결되어 있어야 한다. 

- 네트워크 내에서 컴퓨터들은 무선 네트워크, 혹은 통신 장비나 전송 매체를 통해 연결될 수 있다.

## 네트워크의 종류

- LAN: Local Area Network
  
  - 제한된 영역에서의 작은 네트워크이다.
  
  - LAN은 구축 시에 LAN 외부에서는 내부에 접근할 수 없다. 
  
  - LAN의 예시로는 건물의 한 층의 LAN, 하나의 오피스의 LAN 등이 있을 수 있다.
  
  - 위의 예시에서 볼 수 있듯이, LAN의 핵심은 **외부와 간섭받지 않는, 제한된 영역 내의 컴퓨터들로 구성된 독립된 네트워크**이다.

- WAN: Wide Area Network
  
  - 광역 네트워크라고 불리며 LAN의 집합 / 소규모 네트워크의 집합을 WAN으로 칭한다.
  - 소규모 단위의 네트워크 간 통신을 위한 대규모 네트워크를 WAN이라고 생각하면 된다. 
  - LAN과는 다르게 주로 넓은 범위를 커버하기 때문에 설치 비용이 많이 들며, 실생활에서  매일 사용하는 인터넷은 세계에서 가장 큰 WAN에 속한다. 
  - WAN은 절차와 목적에 따라 계층으로 세분화가 가능하다. OSI(Open Systems Interconnection) 7계층으로 나뉜다.<img title="" src="https://www.cisco.com/c/en/us/products/switches/what-is-a-wan-wide-area-network/jcr:content/Grid/category_atl/layout-category-atl/anchor_info.img.png/1632852916819.png" alt="What Is a WAN? Wide-Area Network" data-align="left"> 

# 인터넷이란?

- Internetworking의 줄인말이며, TPC/IP(Transmission Control Protocol/Internet Protocol) 통신 프로토콜을 이용하여 전 세계의 전자기기가 접속할 수 있도록 하는 네트워크이다. 

- 커버하는 범위가 **전 세계**라는 점에서 네트워크보다 규모가 훨씬 큰, **네트워크의 네트워크**라고 불린다.

- OSI 7 층을 적용할 수 있다. 
  
  - Physical Layer: 네트워크 간의 물리적 데이터 전송을 담당한다. 가장 낮은 계층이다.
  
  - Data Link Layer: 기기 간의 데이터 흐름을 제어한다.
  
  - Network Layer: 네트워크 간 데이터 패킷의 라우팅을 담당한다.
  
  - Transport Layer
  
  - Session Layer
  
  - Presentation Layer
  
  - Application Layer
  
  

# 인터넷의 구성요소

- 구성요소는 크게 두 가지로 나눌 수 있다.

## 1. 네트워크 프로토콜

- IP(Internet Protocol):
  
  - 데이터가 네트워크를 통해 원하는 목적지에 도착할 수 있도록 하기 위해 사용되는 규칙/규약이다.
  
  - TCP/IP 프로토콜을 이용하여 통신하는 서버나 클라이언트 모두는 숫자로 이루어진 IP 주소를 부여받는다. 
  
  - 전송되는 데이터는 작은 조각을 쪼개져서 전송되는데, 이때 쪼개진 조각을 **packet**이라고 부른다.
  
  - 이때 각 패킷에는 IP정보가 주어지고 라우터(router)는 이 정보(패킷의 IP정보, 네트워크 내 각 도메인의 IP주소)를 활용하여 패킷을 올바른 위치로 보낸다. 
  
  ![](C:\Users\kklee\AppData\Roaming\marktext\images\2023-08-15-22-41-45-image.png)
  
  ![IP address gets packets to their destination](https://cf-assets.www.cloudflare.com/slt3lc6tev37/4tzfU9Y5ows0uT3u4GUlWr/9d4eaa83ce372454cc14d5fec83fb5b1/internet_protocol_ip_address_diagram.svg)![IP address gets packets to their destination](https://cf-assets.www.cloudflare.com/slt3lc6tev37/4tzfU9Y5ows0uT3u4GUlWr/9d4eaa83ce372454cc14d5fec83fb5b1/internet_protocol_ip_address_diagram.svg)

- TCP(Transmission Control Protocol)
  
  - 애플리케이션 프로그램과 기기가 네트워크 통신을 통한 정보, 메시지 전달을 가능하게 하는 통신 규약이다. 
  - 데이터가 전송되고 수신되는 방법을 정의하는 것이다.

- HTTP(Hypertext Transfer Protocol)
  
  - 하이퍼텍스트 링크를 활용한 웹페이지를 로딩하는 데 사용되는 프로토콜이다.
  
  - OSI 7계층 중 Application Layer에 포함되며, 네트워크 내 기기 간의 데이터 교환을 위한 통신을 위해 고안되었다.
  
  - 우리가 흔히 아는 서버-클라이언트 간의 통신에서의 request, response 모두 HTTP를 이용한 통신 방법의 하나이다.

- HTTPS(HTTP Secure)
  
  - 기존의 HTTP는 암호화가 되지 않아서 보안에 취약하다는 단점이 있다.
  
  - 이를 보완한 것이 HTTPS이다. HTTPS는 HTTP 메시지를 암호화하여 공격자가 데이터를 탈취하지 못하도록 한다.

## 2. 하드웨어

- 네트워크에 연결되는 모든 기기를 포함한다. 주로 네트워크 하드웨어라고 칭한다.

- Modems(모뎀)
  
  - 컴퓨터가 전화선을 통해 인터넷에 연결하도록 해주는 장치이다.
  
  - 전화선을 통해 인터넷에 연결하기 위해서는 아날로그 신호와 디지털 신호 간의 변환이 필요한데, 모뎀이 신호를 변환해 준다.
  
  - 모뎀은 컴퓨터의 디지털 신호를 아날로그로 변환해 전화선을 통해 보내고, 전화선을 통해 들어온 아날로그 신호를 디지털 신호로 변환한다.

- Routers(라우터)
  
  - 두 개 이상의 네트워크를 연결해 준다.
  
  - 컴퓨터를 LAN이나 WAN에 연결하기 위해서 주로 사용된다.
  
  - 라우터를 활용한 LAN 연결이 바로 우리가 흔히 아는 와이파이다. Wireless Access Points(WAPs)라고 부른다.

- Hubs(허브)
  
  - 네트워크에 연결된 모든 기기로 데이터를 전송시킨다.

- Bridges(브리지)
  
  - 두 독립된 LAN 네트워크를 연결하는 데 사용된다. 

- Switches(스위치)
  
  - 허브와 브리지와 비슷한 역할을 하나 더 효율적이다.
  
  - 네트워크에 연결된 디바이스의 MAC 주소를 저장한 후, 요청이 온 디바이스에만 데이터 패킷을 전송한다. 이러한 방식을 사용하여 통신에서의 latency를 줄인다.

- Network Interface cards(NIC)
  
  - 네트워크에 연결할 수 있도록 돕는 컴퓨터에 연결된 하드웨어 유닛이다.
  
  - 일반적으로 현대의 기기에는 마더보드에 내장 경우가 많다.

- Network cables
  
  - 네트워크에 기기를 연결하기 위해 사용되는 선이다.

- Firewall
  
  - 공격을 막기 위해 컴퓨터와 네트워크 사이에 존재하는 하드웨어나 소프트웨어이다.

![Network Architecture](https://pimages.toolbox.com/wp-content/uploads/2021/12/17142552/Network-Architecture.jpg)

# 

# 네트워크 프로토콜이란?

- 네트워크 프로토콜은 네트워크에 연결된 기기들이 데이터 교환을 쉽고 안전하게 하기 위해 고안된 규약이다.

- 네트워크 프로토콜은 크게 3가지로 분류된다.
  
  1. 네트워크 통신 규약(Network Communication Protocols)
     
     - HTTP(HyperText Transfer Protocol)
     
     - TCP(Transmission Control Protocol)
     
     - IP(Internet Protocol)
     
     - UDP(User Datagram Protocol)
     
     - FTP(File Transfer Protocol)
  
  2. 네트워크 보안 규약(Network Security Protocols)
     
     - SFTP(Secure File Transfer Protocol)
     
     - HTTPS(HyperText Transfer Protocol Secure)
     
     - SSL(Secure Socket Layer)
  
  3. 네트워크 관리 규약(Network Management Protocols)
     
     - SNMP(Simple Network Management Protocol)
     
     - ICMP(Internet Control Message Protocol)
     
     

# Network Edge / Network Core

## Network Edge

- Network Edge는 컴퓨터 네트워크와 외부 네트워크가 연결되기 위한 영역이다.

- 네트워크 입장에서 외부 세계와 통신하기 위해 존재하는 물리적인 영역, 공간, 장치 정도로 생각할 수 있다.

- 직역한 대로 네트워크의 가장자리, 끝부분을 뜻한다.

- 외부와의 통신과 연결을 담당하는 중요한 부분이므로 반드시 아래 3가지 항목을 고려하여 network edge를 설계하여야 한다.
  
  1. Security(보안): 외부와의 연결에서 어떤 공격을 받을지 모르기 때문에 항상 보안에 대비하여야 한다. 보안의 이유로 network edge 영역에 방화벽과 같이 침입을 방지하기 위한 장치가 설치된다.
  
  2. Redundancy(중복성/용장성): 오류로 인해 network edge가 정상적으로 동작하지 않을 경우, 인터넷 연결이 중단되거나 하는 문제가 발생할 수 있기 때문에 redundancy(필요량 이상이 있음을 말함)를 고려한 설계가 요구된다.
  
  3. WAN optimization(최적화): VOIP와 같은 기능을 위해 고품질의 통신 성능이 요구되는 경우가 있고 이를 위해서 최적화가 요구된다. 
  
  ![Diagram showing a network edge - TeleDynamics Blog](https://info.teledynamics.com/hs-fs/hubfs/blog-images/network%20edge.png?width=642&name=network%20edge.png)



## Network Core

- Backbone network(백본망)이라고 불리기도 하며, 네트워크 노드 사이의 효율적이고 안정적인 트래픽 흐름을 담당한다.

- 하위 네트워크를 상호 연결하고 분산된 망을 통합하는 역할을 한다.

- 주로 routers와 switches가 사용된다.

- 네트워크 통신의 중심이며 심장과도 같은 역할을 한다. 엣지 네트워크를 연결하는 네트워크 중심에 위치한 네트워크이다.
  
  ![](https://blog.kakaocdn.net/dn/8ggWx/btqwpTJFxZb/0ytsd0y1eRqjN3PG9ExciK/img.png)



### 참고자료:

[What Are Network Protocols? - IT Glossary | SolarWinds](https://www.solarwinds.com/resources/it-glossary/network-protocols)

https://www.cloudflare.com/learning/ddos/glossary/hypertext-transfer-protocol-http/

https://www.cloudflare.com/learning/network-layer/internet-protocol/

https://www.javatpoint.com/network-vs-internet

[What is the Internet? Definition from WhatIs.com.](https://www.techtarget.com/whatis/definition/Internet)

https://www.objc.io/issues/10-syncing-data/ip-tcp-http/

[Network edge vs. edge computing](https://info.teledynamics.com/blog/network-edge-vs-edge-computing)

[리던던시](http://www.ktword.co.kr/test/view/view.php?m_temp1=1217)

[#2. 네트워크 엣지](https://asparait.tistory.com/11)
