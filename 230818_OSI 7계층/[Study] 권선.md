# OSI 7계층이란?

## OSI 7계층 (Open Systems Interconnection Model의 7 Layer)

	네트워킹에서 통신 프로세스를 일련의 계층으로 분류한 것입니다. 이 모델은 1980년대에 국제 표준화 기구 (ISO)에 의해 개발되었습니다. OSI 7계층은 복잡한 네트워크 통신 과정을 분해하여 각 계층이 수행하는 특정한 기능을 명확하게 이해하게 도와줍니다.

## OSI 7계층의 개요

### 물리 계층 (Physical Layer)

	기능: 비트(bit) 단위로 데이터를 전송합니다. 전기적, 기계적, 기능적 특성을 정의합니다.
	장치: 허브, 리피터
	예: 케이블, 스위치, RJ-45 커넥터

### 데이터 링크 계층 (Data Link Layer)

	기능: 프레임(frame) 단위로 데이터를 전송하며, 오류 검출 및 오류 수정을 수행합니다.
	장치: 브리지, 스위치
	예: MAC 주소, 프레임, 오류 검출 및 수정

### 네트워크 계층 (Network Layer)

	기능: 데이터 패킷의 경로를 결정하고 라우팅합니다.
	장치: 라우터
	예: IP 주소, 라우팅

### 전송 계층 (Transport Layer)

	기능: 데이터 전송의 신뢰성 및 흐름 제어를 담당합니다.
	예: TCP, UDP

### 세션 계층 (Session Layer)

	기능: 통신 세션을 설정, 관리 및 종료합니다.
	예: NetBIOS, RPC

### 표현 계층 (Presentation Layer)

	기능: 데이터의 변환, 암호화 및 압축을 담당합니다.
	예: JPEG, MPEG, 암호화
	
### 응용 계층 (Application Layer)

	기능: 사용자와 가장 가까운 계층으로, 애플리케이션 및 네트워크 서비스에 대한 인터페이스를 제공합니다.
	예: HTTP, FTP, SMTP, DNS

# OSI 7계층 계층별 기능, 프로토콜 종류

## OSI 7계층 계층별 기능

### 1. 물리 계층 (Physical Layer)
   - 데이터의 비트(bit) 단위 전송.
   - 케이블 유형, 신호 전송 방식, 핀 배치, 전압 등 물리적 특성 정의.
   - 디지털 신호를 아날로그 신호로, 또는 그 반대로 변환.

### 2. 데이터 링크 계층 (Data Link Layer)
   - 프레임(frame) 단위로 데이터의 안전한 전송을 보장.
   - 오류 검출 및 수정 기능 (예: CRC, Checksum).
   - MAC 주소를 사용한 프레임의 주소 지정.
   - 스위치나 브리지와 같은 장치의 작동 원리를 규정.

### 3. 네트워크 계층 (Network Layer)
   - 데이터 패킷의 경로를 결정 및 라우팅.
   - IP 주소 지정 및 라우팅 경로 선택.
   - 다양한 네트워크 간의 연결과 데이터 전송.

### 4. 전송 계층 (Transport Layer)
   - 포트 주소를 사용하여 특정 프로세스 간의 통신을 가능하게 함.
   - 데이터의 전송 신뢰성 및 흐름 제어 (예: TCP에서의 재전송).
   - 세그먼트 생성 및 재조립.

### 5. 세션 계층 (Session Layer)
   - 통신 세션을 생성, 관리, 및 종료.
   - 데이터 전송의 동기화 및 연속성 관리.
   - 양방향 통신을 위한 세션 설정.

### 6. 표현 계층 (Presentation Layer)
   - 사용자 시스템과 네트워크 간의 데이터 형식 변환.
   - 암호화 및 복호화.
   - 데이터의 압축 및 해제.

### 7. 응용 계층 (Application Layer)
   - 사용자 인터페이스와 네트워크 사이의 인터페이스 제공.
   - 네트워크 서비스와 직접 상호작용하는 애플리케이션 서비스 제공.
   - 사용자의 요청 및 서비스 실행 (예: 이메일, 웹 브라우징).

## 계층별 프로토콜 종류

### 1. 물리 계층 (Physical Layer) 프로토콜
<details>
   <summary>- USB (Universal Serial Bus)</summary>
기기 간의 연결과 데이터 전송을 위한 표준.
</details>
<details>
   <summary>- Ethernet (전기적/광학적 신호의 규정)</summary>
유선 네트워크에서 데이터 전송을 위한 전기적/광학적 표준.
</details>
<details>
   <summary>- Bluetooth (무선 신호의 규정)</summary>
무선 통신을 위한 짧은 거리의 데이터 전송 표준.
</details>

### 2. 데이터 링크 계층 (Data Link Layer) 프로토콜
<details>
   <summary>- Ethernet (MAC 주소를 활용한 프레임 전송 규약)</summary>
프레임의 포맷 및 MAC 주소를 사용한 장치 간 통신 표준.
</details>
<details>
   <summary>- PPP (Point-to-Point Protocol)</summary>
직접적인 연결(예: 전화선)을 사용하여 두 지점 간의 데이터 전송을 위한 프로토콜.
</details>
<details>
   <summary>- HDLC (High-Level Data Link Control)</summary>
데이터 링크 제어와 오류 관리를 위한 프로토콜.
</details>

### 3. 네트워크 계층 (Network Layer) 프로토콜
<details>
   <summary>- IP (Internet Protocol)</summary>
데이터 패킷의 송수신과 라우팅을 위한 주소 지정 프로토콜.
</details>
<details>
   <summary>- ICMP (Internet Control Message Protocol)</summary>
네트워크 계층의 오류 보고 및 진단 메시지 전송.
</details>
<details>
   <summary>- OSPF (Open Shortest Path First)</summary>
다양한 네트워크 환경에서 최적의 라우팅 경로 선택을 위한 프로토콜.
</details>

### 4. 전송 계층 (Transport Layer) 프로토콜
<details>
   <summary>- TCP (Transmission Control Protocol)</summary>
신뢰성 있는 연결 지향적인 데이터 전송과 흐름 제어를 위한 프로토콜.
</details>
<details>
   <summary>- UDP (User Datagram Protocol)</summary>
연결 없이 데이터를 빠르게 전송하는 프로토콜.
</details>
<details>
   <summary>- SCTP (Stream Control Transmission Protocol)</summary>
TCP와 유사하지만 다양한 서비스 및 보안 기능 제공.
</details>

### 5. 세션 계층 (Session Layer) 프로토콜
<details>
   <summary>- NetBIOS</summary>
네트워크 상의 기기나 서비스의 이름을 해석하여 주소를 찾는 프로토콜.
</details>
<details>
   <summary>- RPC (Remote Procedure Call)</summary>
다른 컴퓨터에 위치한 프로그램 또는 서비스를 호출하기 위한 프로토콜.
</details>
<details>
   <summary>- PPTP (Point-to-Point Tunneling Protocol)</summary>
VPN 연결을 위한 터널링 프로토콜.
</details>


### 6. 표현 계층 (Presentation Layer) 프로토콜
<details>
   <summary>- SSL/TLS (Secure Sockets Layer/Transport Layer Security)</summary>
네트워크 연결의 보안 및 데이터 암호화를 위한 프로토콜.
</details>
<details>
   <summary>- JPEG, GIF (그래픽 포맷 변환)</summary>
그래픽 이미지의 압축 및 표현 포맷.
</details>
<details>
   <summary>- MPEG, WAV (오디오/비디오 포맷 변환)</summary>
오디오 및 비디오 데이터의 압축 및 표현 포맷.
</details>

### 7. 응용 계층 (Application Layer) 프로토콜
<details>
   <summary>- HTTP/HTTPS (Hypertext Transfer Protocol/Secure)</summary>
웹 브라우저와 웹 서버 간의 정보 요청 및 전송.
</details>
<details>
   <summary>- FTP (File Transfer Protocol)</summary>
파일의 업로드와 다운로드를 위한 프로토콜.
</details>
<details>
   <summary>- SMTP (Simple Mail Transfer Protocol)</summary>
이메일 메시지의 전송을 위한 프로토콜.
</details>
<details>
   <summary>- DNS (Domain Name System)</summary>
도메인 이름을 IP 주소로 변환하는 서비스.
</details>
<details>
   <summary>- DHCP (Dynamic Host Configuration Protocol)</summary>
네트워크에 연결된 장치에 동적으로 IP 주소를 할당하는 프로토콜.
</details>

# 송신 -> 수신 (OSI 7계층을 기준으로 정리)

## 1. 물리 계층 (Physical Layer)
    - **송신**: 응용 계층에서 내려온 데이터를 비트(bit)로 변환하여 통신 매체(예: 케이블, 무선)를 통해 전송합니다.
    - **수신**: 전송된 비트를 수신하고, 프레임으로 변환하여 상위 계층에 전달합니다.

## 2. 데이터 링크 계층 (Data Link Layer)
    - **송신**: 데이터를 프레임(frame)으로 변환하고, MAC 주소를 사용하여 소스와 목적지를 식별합니다.
    - **수신**: 프레임을 수신하고, 오류 검사를 수행한 뒤 올바른 목적지로 전달합니다.

## 3. 네트워크 계층 (Network Layer)
    - **송신**: 최적의 경로를 선택하여 데이터 패킷을 전송합니다. IP 주소를 사용하여 소스와 목적지를 식별합니다.
    - **수신**: 패킷의 목적지 IP 주소를 확인하고, 해당 패킷을 적절한 경로로 전달합니다.

## 4. 전송 계층 (Transport Layer)
    - **송신**: 전체 데이터를 세그먼트(segment)로 분할하고, 수신측에 재조립할 수 있도록 정보를 추가합니다.
    - **수신**: 세그먼트를 다시 조립하여 원래의 데이터 스트림으로 복원합니다.

## 5. 세션 계층 (Session Layer)
    - **송신**: 데이터 통신의 세션을 설정, 관리, 종료합니다.
    - **수신**: 도착한 데이터의 세션 정보를 확인하고, 세션을 유지하거나 종료합니다.

## 6. 표현 계층 (Presentation Layer)
    - **송신**: 데이터를 암호화, 압축, 변환합니다.
    - **수신**: 수신된 데이터의 암호화 해제, 압축 해제, 변환을 수행합니다.

## 7. 응용 계층 (Application Layer)
    - **송신**: 사용자가 데이터(예: 웹 페이지 요청, 이메일 전송)를 생성하면, 응용 계층에서는 해당 데이터를 하위 계층으로 전달하기 위한 형식으로 변환합니다.
    - **수신**: 전송된 데이터를 원래의 형식으로 변환하여 사용자에게 제공합니다.

