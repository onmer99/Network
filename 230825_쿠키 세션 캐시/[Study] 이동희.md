# 쿠키(Cookie)

## 쿠키란 무엇인가?

HTTP의 특징에는 Stateless(무상태성), Connectionless(비연결성)을 지닌다.

- Connectionless: 클라이언트의 요청을 서버가 받고 서버가 응답을 보내주는 과정이 끝나면 통신이 끊어지는 특징

- Stateless: 통신이 끝나면 상태를 유지하지 않는 특징(예: 로그인. 통신이 끝나면 로그인 상태 또한 사라진다)

두 특성 때문에 서버는 클라이언트의 신원을 식별하기 위해서 매번 인증 절차를 거쳐야 하는데, 매번 **인증을 거치는 것을 해결하기 위해서 존재하는 것**이 **쿠키**이다. 인증과 마찬가지로 상태 유지를 위해서도 사용된다.

쇼핑몰에서 물건을 주문을 한다고 할 때, 쿠키가 없다면...

로그인 -> 제품 상세 페이지로 이동 -> 로그인 -> 제품 주문 페이지로 이동 -> 로그인 ... 과 같이 페이지를 이동할 때마다 매번 로그인이라는 인증 과정을 거쳐야 할 것이다.



## 쿠키의 구성요소

- 이름: 쿠키를 식별하는 데에 사용되는 이름.

- 값: Key-Value 형태의 데이터를 담는다.

- 유효시간: 쿠키에 명시된 유효시간이 지나면 쿠키는 삭제된다. 

- 도메인: 쿠키를 전송할 도메인. 쿠키를 어떤 도메인으로 전송할지에 대한 정보를 담는다.

- 경로: 쿠키를 전송할 요청 경로. 쿠키를 어떤 경로로 보낼지에 대한 정보를 담는다.



### 쿠키의 동작

1. 클라이언트에서 서버로 요청을 보내면 서버는 쿠키를 생성한다.

2. 서버는 생성한 쿠키를 HTTP의 Header 부분에 포함시켜서 클라이언트에게 응답으로 보낸다.

3. 클라이언트는 해당 쿠키를 받아서 유효기간까지 보관한다. 이 때 브라우저가 종료되어도 쿠키는 삭제되는 것이 아니라 클라이언트가 보관한다.

4. 클라이언트가 서버에 같은 요청을 할 경우 HTTP Header에 쿠키를 포함시켜 보낸다.

5. 서버에서 쿠키를 읽고 인증/상태 유지에 사용한다. 정보의 변경사항이 있을 경우 쿠키의 정보를 업데이트하고 클라이언트로 다시 응답을 통핸 전송한다.

![](https://blog.kakaocdn.net/dn/betTb6/btqxVesqYq0/sUO2b5dpKqVuR261lNZBKk/img.png)



## 쿠키의 종류

1. Session Cookie: 부라우저가 열려있는 동안만 유지되는 쿠키이다. 브라우저가 종료되면 쿠키가 삭제된다.

2. Persistent Cookie: 브라우저가 종료되어도 만료일자까지 유지된다. 

3. Secure Cookie: 로그인 정보, 개인 정보와 같은 민감한 데이터를 보호하기 위해서 HTTPS에서 전송되는 쿠키이다.

4. Third-Party Cookie: 사용자가 방문한 웹사이트와는 별개인 도메인의 서드파티 서버에서 생성되고 관리되는 쿠키. 주로 사용자 맞춤형 광고를 위해 활용된다.



# 세션(Session)

## 세션이란 무엇인가?

기존의 쿠키 방식은 쿠키가 노출될 경우 보안 문제가 발생할 수 있다. 이를 방지하기 위해서 **세션에서는 민감정보를 쿠키에 저장하지 않고 서버에 저장한다.**

서버는 유저의 식별자인 SessionID에 해당하는 각종 정보를 저장한다.

브라우저가 종료되면 세션 또한 종료된다. 세션도 마찬가지로 일정 시간이 지나면 세션이 종료되도록 할 수 있다. 이를 **Session Timeout**이라고 한다.



## 세션의 동작

1. 클라이언트가 서버로 요청을 보낸다.

2. 서버는 세션ID가 담긴 쿠키를 생성하여 클라이언트로 응답을 보낸다.

3. 클라이언트는 다시 서버에게 요청을 보낼 때 세션ID가 담긴 쿠키를 보낸다.

4. 서버는 쿠키를 통해 세션ID를 전달받아 세션ID에 해당하는 정보를 사용하여 작업한다.

5. 세션ID에 해당하는 정보를 활용하여 서버 요청 처리 후 클라이언트에게 응답한다.



## 쿠키와 세션의 차이점은 무엇인가?

- 정보가 저장되는 위치
  
  - 쿠키: 클라이언트, 브라우저에 정보가 저장된다.
  
  - 세션: 서버에 세션ID에 해당하는 정보가 저장된다.

- 요청속도는 쿠키가 세션보다 빠르다. 세션은 서버에서 정보처리가 이루어지기 때문이다.

- 보안 측면에서는 세션이 쿠키보다 우수하다.

- 쿠키는 브라우저가 종료되어도 만료기간이 남아있다면 삭제되지 않지만, 세션은 만료기간과 관계없이 브라우저가 종료되면 삭제된다.



# 캐시(Cache)

## 캐시란 무엇인가?

캐시는 정보를 임시적으로 저장하여 빠르게 접근할 수 있도록 하는 장치, 저장소 등을 뜻한다. 주로 불러오는 빈도가 잦은 정보나, 접근 시간이 오래 걸리는 정보를 캐시에 저장한다. 

캐시에 데이터를 저장해놓으면 데이터가 필요할 때마다 매번 서버에 요청할 필요가 없이 캐시 접근해 데이터를 불러오기 때문에 데이터 접근 시간, 소요 자원, 네트워크 부하 측면에서 매우 효율적이다.

파레토 법칙에 따라 20%의 요구사항이 80%의 리소스를 사용할 때가 많은데, 실제 서비스에서 요구하는 20%의 데이터를 캐시를 활용하여 리소스양을 줄이고, 성능을 향상시킬 수 있다.

![사회복지정책 - 빌프레토 파레토의 파레토 법칙(배분적 효율) : 네이버 블로그](https://mblogthumb-phinf.pstatic.net/MjAxNzAzMTRfMTUx/MDAxNDg5NDU4MjQwNTA3.oMtnEKoLZLfE8osHZsJrdqjkTyRgbdm1Lt1pu6cjqNcg.ELrq1UqEsI4vtRMMXk4pmGZr5swNFIOI6UJW7duKluAg.JPEG.sparkman7/adv15_1.jpg?type=w800)



## 캐시의 종류

1. Local Cache
   
   - Local 장비에서 활용된다.
   
   - Local 장비의 Resource를 활용한다(Memory)
   
   - Local 장비 내에서 활용되기 때문에 속도가 빠르다.

2. Global Cache
   
   - 별도의 Cache Server를 두고 사용한다.
   
   - 네트워크 트래픽을 통한 캐시이기 때문에 속도가 Local Cache보다 느리다.
   
   

## 참고자료

[쿠키와 세션 개념](https://interconnection.tistory.com/74)

[[Network] 쿠키(Cookie)란? (What is a Cookie?)](https://fomaios.tistory.com/entry/Network-%EC%BF%A0%ED%82%A4Cookie%EB%9E%80-What-is-a-Cookie)

[웹브라우저 쿠키란? - 쿠키 개념, 세션 개념 (Cookie &amp; Session)](https://lovefor-you.tistory.com/247)

https://www.cloudflare.com/ko-kr/learning/privacy/what-are-cookies/

[HTTP 쿠키 - HTTP | MDN](https://developer.mozilla.org/ko/docs/Web/HTTP/Cookies)

https://velog.io/@xchdtk/HTTP-%EC%BF%A0%ED%82%A4Cookie-%EC%84%B8%EC%85%98Session%EC%9D%98-%EC%9D%B4%ED%95%B4

[ssh 연결 타임 아웃 지정(ssh connection timeout)](https://www.lesstif.com/lpt/ssh-ssh-connection-timeout-100205209.html)

[cash? cache? 캐시란 무엇인가](https://wh00300.tistory.com/79)

[[Server] Cache(캐시)란? - MangKyu's Diary](https://mangkyu.tistory.com/69)

[[Network] 캐시(Cache) 알아보기 — 일단은 내 이야기](https://kdhyo98.tistory.com/88)
