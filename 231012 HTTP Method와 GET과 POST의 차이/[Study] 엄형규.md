

## GET 방식

요청 방식 : 파라미터(url?파라미터name="파라미터Value")

특이점 : 

+ 데이터를 받는 용도로 사용하므로 DB에 변화를 주지 않는다.
+ 캐시 처리가 가능하다.
+ 길이 제한이 있다.
+ 브라우저 히스토리에 남는다.

![image-20231012131556009](C:\Users\교육생\AppData\Roaming\Typora\typora-user-images\image-20231012131556009.png)



## POST 방식

요청 방식 : 모두 가능 

헤더 : Content-Tpye에 데이터 타입을 표시해야한다. ex) application/x-www-form-urlencoded, text/plain, multipart/form-data

*데이터 타입을 표시하지 않는 경우 rul에 포함된 리소스의 확장자 명으로 데이터 타입을 유추한다.

특이점 : 

+ 브라우저 히스토리에 남지 않는다.
+ 길이 제한이 없다.
+ 보낼 때마다 Non-idempotent하기 때문에 매번 다른 응답을 받게된다.

![image-20231012131607833](C:\Users\교육생\AppData\Roaming\Typora\typora-user-images\image-20231012131607833.png)

![image-20231012132729913](C:\Users\교육생\AppData\Roaming\Typora\typora-user-images\image-20231012132729913.png)



## PUT 방식

PUT 메서드는 리소스 전체를 대체한다. 기존 리소스가 없을 경우 새로 생성한다. 즉, 덮어쓰기를 수행한다고 볼 수 있다. POST와 차이점은 클라이언트가 리소스의 위치를 알고 URI를 명시해야 한다는 점이다.


## PATCH 방식
PATCH 메서드는 리소스를 부분 변경한다. 부분 변경이 필요한 상황에서 PATCH를 사용할 수 없다면 POST를 사용한다.

## DELETE 방식
DELETE 메서드는 리소스를 제거한다.