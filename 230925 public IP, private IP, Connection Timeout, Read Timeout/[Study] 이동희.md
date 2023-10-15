# Connection TimeOut vs Read TimeOut

<aside>
💡 Connection Timeout

</aside>

Connection Timeout에서의 timeout을 판별하는 기준은 **종단 간 연결하는데 소요되는 시간**이다.

연결하는데 최대 허용 시간을 넘기게 되면 데이터를 받을 수 없는 것으로 간주하고 에러를 발생시킨다.

![Untitled.png](C:\Users\kklee\AppData\Local\Temp\BNZ.65107437276d51c5\Untitled.png)

[https://afteracademy.com/blog/what-is-a-tcp-3-way-handshake-process/](https://afteracademy.com/blog/what-is-a-tcp-3-way-handshake-process/)

위와 같은 TCP 3-Way Handshaking으로 클라이언트가 서버가 통신한다고 할 때, 첫번째 단계에서 클라이언트가 연결을 위해 서버로 SYN을 보낼 때, 설정한 대기 시간을 넘어서 연결 지연이 지속되는 것이 **Connection Timeout**이다. 

<aside>
💡 Read Timeout

</aside>

Connection Timeout과는 다르게 클라이언트와 서버간의 연결은 성공했으나, 클라이언트가 서버로 요청 데이터를 전송한 경우에 발생한다.

클라이언트가 서버로 요청데이터를 전송하였으나, 설정한 대기 시간을 넘는 시간동안 응답 데이터를 받지 못하는 경우가 **Read Timeout**이다. 

<aside>
💡 Read Timeout과 Connection Timeout의 차이

</aside>

![Untitled 1.png](C:\Users\kklee\AppData\Local\Temp\BNZ.65107452276dbc66\Untitled%201.png)

[https://alden-kang.tistory.com/20](https://alden-kang.tistory.com/20)

**Connection Timeout**은

종단 간에 연결지연이 계속되어 설정한 시간 값을 넘어갈 때 발생한다.

**Read Timeout**은

종단 간에 연결은 완료된 상태이나, 클라이언트 측에서 요청한 데이터가 설정한 시간 값을 넘어가도 응답 데이터로 오지 않아 발생한다.

<aside>
💡 참고출처

</aside>

[https://inyl.github.io/programming/2017/12/02/timeout.html](https://inyl.github.io/programming/2017/12/02/timeout.html)

[https://alden-kang.tistory.com/20](https://alden-kang.tistory.com/20)

[https://hoi5088.medium.com/connection-time-out-과-read-time-out-그리고-해결-및-이슈-1b011d3cb29d](https://hoi5088.medium.com/connection-time-out-%EA%B3%BC-read-time-out-%EA%B7%B8%EB%A6%AC%EA%B3%A0-%ED%95%B4%EA%B2%B0-%EB%B0%8F-%EC%9D%B4%EC%8A%88-1b011d3cb29d)

[https://romainefabula.tistory.com/87](https://romainefabula.tistory.com/87)

[https://velog.io/@byeongju/ConnectionTimeout과-ReadTimeout은-어떤-값이-적절할까](https://velog.io/@byeongju/ConnectionTimeout%EA%B3%BC-ReadTimeout%EC%9D%80-%EC%96%B4%EB%96%A4-%EA%B0%92%EC%9D%B4-%EC%A0%81%EC%A0%88%ED%95%A0%EA%B9%8C)



# 공인 IP vs 사설 IP

💡 IP 주소란?

IP 주소는 인터넷에 연결된 장치가 웹서버와 통신하는 데 사용됨. 인터넷 프로토콜(Internet Protocol) 주소를 의미하고 숫자로 구성되어 있음. **인터넷에 연결된 장치를 식별**하는 역할을 함.

IP주소는 버전에 따라 IPv4, IPv6로 구분 됨.

**IPv4**: 네 구간의 숫자로 구성되어 있음. x.x.x.x와 같이 점으로 구분. 각 숫자는 0~255 숫자로 구성됨.

**IPv6**: 주소가 숫자와 알파벳이 포함된 16진법으로 구성됨. 암호화와 인증 기능 제공함.

IP 주소에는 **사설 IP**와 **공인 IP**가 존재함.



💡 공인 IP

인터넷 사업자(ISP)가 사용자에게 할당함.

공유기가 인터넷과 통신하도록 하는 역할을 하는 외부 IP 주소임.

공인 IP 주소는 전체 네트워크에 적용됨. 해당 네트워크에 접속한 기기는 모두 공인 IP 주소를 가지기 때문에 IP주소를 공유한다고 하여, **네트워크가 공동으로 사용하는 IP를 공용 IP 주소**라고 한다.

외부에 공개되어 있는 IP 주소이며 중복이 없는 유일한 IP 주소이다.



💡 사설 IP

공인 IP 주소와 다르게 네트워크에 연결된 장치에 할당된 내부 IP 주소임.

가정, 회사 등 로컬 네트워크에서 할당되며 다른 네트워크 IP 주소와는 중복이 가능함.



💡 사설 IP와 공인 IP의 차이

![Untitled.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651074dd276fda06\Untitled.png)

[공인 IP와 사설 IP… 다양한 IP 유형의 차이는? | NordVPN](https://nordvpn.com/ko/blog/public-ip-and-private-ip/)



💡 데이터 송수신

![Untitled 1.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651074c6276f808c\Untitled%201.png)

**데이터를 보낼 때는**

사설 IP를 할당받은 컴퓨터나 휴대폰 같은 기기가 데이터 패킷을 인터넷으로 전송하면, 라우터는 기기의 사설 IP를 공인 IP로 바꾸어 전송한다.

**데이터를 받을 때는**

인터넷을 통해 데이터 패킷이 들어오고, 데이터 패킷은 공인 IP로 해당하는 라우터로 데이터가 전송된다. **NAT(Network Access Translation)** 기술을 통해 공인 IP는 사설 IP로 변환되고 기기로 데이터 패킷이 전송된다.



💡 참고출처

[공인 IP와 사설 IP… 다양한 IP 유형의 차이는? | NordVPN](https://nordvpn.com/ko/blog/public-ip-and-private-ip/)

[https://velog.io/@hidaehyunlee/공인Public-사설Private-IP의-차이점](https://velog.io/@hidaehyunlee/%EA%B3%B5%EC%9D%B8Public-%EC%82%AC%EC%84%A4Private-IP%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90)

[https://inpa.tistory.com/entry/WEB-🌐-IP-기초-사설IP-공인IP-NAT-개념-정말-쉽게-정리](https://inpa.tistory.com/entry/WEB-%F0%9F%8C%90-IP-%EA%B8%B0%EC%B4%88-%EC%82%AC%EC%84%A4IP-%EA%B3%B5%EC%9D%B8IP-NAT-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A7%90-%EC%89%BD%EA%B2%8C-%EC%A0%95%EB%A6%AC)

[Public IP, Private IP(공인IP, 사설IP)](https://skstp35.tistory.com/280)