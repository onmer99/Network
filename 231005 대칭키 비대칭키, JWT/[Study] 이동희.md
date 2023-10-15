# 대칭키 / 비대칭키 암호화 방식

<aside>
💡 대칭키 암호화

</aside>

암호화, 복호화에 사용되는 키가 동일한 암호화 방식이다.

대표적인 알고리즘으로는 **DES, 3DES, AES, SEED, ARIA**가 있다.

즉, 정보를 암호화하여 전달하고, 전달받은 정보를 복호화하여 확인하기 위해 동일한 키가 필요하다. 

![Untitled.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651e17dd5cb4d51a\Untitled.png)

하지만 암호화/복호화에 사용되는 키가 동일하기 때문에 암호화 과정을 거친 후에 정보를 전달하더라도 복호화를 위해 결국 키를 전송해야한다.

속도가 빠르다는 장점이 존재하지만, 키 전송 과정에서 키를 탈취당할 경우, 암호화된 정보가 유출될 위험이 존재한다.

키가 많아지면 키 관리가 어렵고, 키 배송 및 키 탈취에 대한 위험이라는 단점이 존재한다.

이를 보완하기 위해 고안된 것이 비대칭키 암호화 방식이다.

<aside>
💡 비대칭키(공개 키) 암호화

</aside>

암호화, 복호화에 사용되는 키가 다른 암호화 방식이다.

![Untitled 1.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651e17f85cb5418f\Untitled%201.png)

암호화에는 비대칭키 암호화에는 두 가지 방식이 존재한다.

1. 공개키로 암호화: 공개키로 암호화를 할 경우, 개인키로 복호화를 해야한다.
2. 개인키로 암호화: 개인키로 암호화를 할 경우, 공개키로 복호화를 해야한다. 

공개키로 암호화, 개인키로 복호화의 경우는 데이터 자체에 대한 암호화가 필요한 경우 사용한다.

개인키로 암호화, 공개키로 복호화의 경우에는 데이터를 보낸 사람이 누구인지, 송신자의 정보에 대한 검증이 필요할 때 사용한다.

안전한만큼 속도가 느리다는 단점이 존재한다.

<aside>
💡 참고출처

</aside>

[https://universitytomorrow.com/22](https://universitytomorrow.com/22)

[https://www.uname.in/129](https://www.uname.in/129)

[https://myjamong.tistory.com/293](https://myjamong.tistory.com/293)

[https://velog.io/@octo__/대칭키와-공개키비대칭키](https://velog.io/@octo__/%EB%8C%80%EC%B9%AD%ED%82%A4%EC%99%80-%EA%B3%B5%EA%B0%9C%ED%82%A4%EB%B9%84%EB%8C%80%EC%B9%AD%ED%82%A4)



# JWT란

💡 토큰이란?

HTTP 통신은 **stateless 특성(무상태성: 통신의 상태를 저장 및 보존하지 않는 특성)** 때문에 웹 페이지를 이동할 때마다 매번 **인증과 인가**를 위한 로그인을 하여야 하는 불편함이 존재할 것이다.

**인증과 인가**에는 차이가 있는데,

**인증은** 로그인으로 생각하면 편한데, 클라이언트 상에서 해당 이용자가 본인임을 증명하는 과정이다. 유저는 유저 아이디와 패스워드를 입력하여 본인임을 **인증**하고 해당 인증이 성공적일 경우에 로그인이 완료된다.

**인가**는 특정 유저에게 권한을 부여하는 것이다. 인증이 된 유저가 특정 자원에 접근하기 위해서는 **인가**가 필요할 것이다.

이를 해결하기 위한 기술이 바로 **세션/토큰**이다. 웹서비스 상에서 본인 **인증** 수단이 필요할 때가 있는데 이 때 사용되는 것이 바로 **토큰**이다.

로그인이 완료되면 서버는 토큰을 클라이언트에게 발급한다. 토큰이 존재하기 때문에 유저는 매번 로그인을 통한 **인증**과정을 거치지 않아도 된다. (토큰 == 신분증)

발급된 토큰은 웹 브라우저에 저장된다. 서버로 새로운 request를 보낼 때마다 **인가**를 위해 발급된 토큰을 같이 보낸다.



![Untitled.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651e187b5cb73fff\Untitled.png)



💡 JWT의 구조

**JSON Web Token**을 줄여서 JWT라고 부른다.

JWT는 세 부분으로 나누어진다.

1. 헤더(Header)
2. 내용(Payload)
3. 서명(Signature)

![img1.daumcdn.png](C:\Users\kklee\AppData\Local\Temp\BNZ.651e18915cb79534\img1.daumcdn.png)



**헤더**에는 토큰의 타입과 암호화 알고리즘(해시 알고리즘)의 종류가 담겨있다.

**내용(Payload)**에는 JWT에 담기는 핵심 데이터, 실제 서버와 클라이언트 간에 통신에서 주고받고자 하는 데이터가 담긴다. **내용(Payload)**에 담기는 **key-value 형식**으로 이루어진 한쌍의 데이터를 **Claim**이라고 한다.

Claim의 종류는 크게 **3가지**로 나뉜다.

**Registered Claim**: 토큰 정보를 표기하기 위해 이름이 정해진 데이터(이미 약속 되어 있음)

- iss(issuer; 발행자),
- exp(expireation time; 만료 시간),
- sub(subject; 제목),
- iat(issued At; 발행 시간),
- jti(JWI ID)

```json
{
 "iss": "dev-coco.tistory.com", // Registered
 "exp": "1602076408", // Registered
 "https://dev-coco.tistory.com/jwt": true, // Public
 "userId": "dev-coco" // Private
 "username": "coco" // Private
}
```

**Public Claim**: 사용자 정의 클레임

**Private Claim**: 토큰을 주고 받는 당사자들 간에 정보 공유를 위한 사용자 정의 클레임. 해당 데이터를 이용하여 유저를 특정할 수 있다.

**서명(Signature)**에는 **헤더**에서 정의한 알고리즘으로 **인코딩한 헤더 값** + **인코딩한 내용(Payload) 값** + **서버의 secret key**값을 더한 것을 인코딩 한 것이다.

**헤더와 내용(Payload)**는 단순히 인코딩 된 값이기 때문에 복호화 또는 조작이 가능하지만, **서명(Signature)**는 서버의 secret key를 알지 못하는 이상, 복호화가 불가능하다. 따라서 **서명(Signature)**는 토큰의 **위변조 여부**를 판단하는데 사용된다.

💡 JWT의 단점

토큰의 주 목적은 정보 보호가 아닌 위조 방지이다.

1. 앞서 말했듯이, JWT 토큰에 저장되는 값은 인코딩 된 값이기 때문에 복호화가 가능하다. 따라서 비밀번호와 같은 민감한 정보는 애초에 토큰의 내용(Payload)에 담지 않는 것이 좋다.
2. 정보가 많아질수록 토큰의 길이 또한 길어지게 되고 네트워크에 부하를 줄 수 있다.
3. 토큰을 탈취당하면 대처하기가 어렵다.

토큰 탈취 위험을 막기 위해 Access Token과 Refresh Token이 사용된다.

💡 참고출처

[https://inpa.tistory.com/entry/WEB-📚-JWTjson-web-token-란-💯-정리#token_인증](https://inpa.tistory.com/entry/WEB-%F0%9F%93%9A-JWTjson-web-token-%EB%9E%80-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC#token_%EC%9D%B8%EC%A6%9D)

[https://velog.io/@syoung125/JWT-토큰이란](https://velog.io/@syoung125/JWT-%ED%86%A0%ED%81%B0%EC%9D%B4%EB%9E%80)

[https://velog.io/@chickenrun/세션-인증-방식-VS-Token-인증방식인증과-인가#토큰-기반-인증-방식jwt](https://velog.io/@chickenrun/%EC%84%B8%EC%85%98-%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EC%8B%9D-VS-Token-%EC%9D%B8%EC%A6%9D%EB%B0%A9%EC%8B%9D%EC%9D%B8%EC%A6%9D%EA%B3%BC-%EC%9D%B8%EA%B0%80#%ED%86%A0%ED%81%B0-%EA%B8%B0%EB%B0%98-%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EC%8B%9Djwt)

https://hudi.blog/session-based-auth-vs-token-based-auth/

[[인증/인가]Session(세션)과 Token(토큰)(JWT)의 차이점](https://fierycoding.tistory.com/69)

[JWT(Json Web Token) 란 무엇일까? (서버 기반 인증 / 토큰 기반 인증)](https://dev-coco.tistory.com/103#head5)