# WebSocket
웹버전의 TCP또는 소켓이다.

웹에서 실시간 처리를 가능하게한 기술이다.

웹에서 주로 사용하던 protocol은 HTTP protocol이다. 

HTTP protocol의 특징은 연결이 유지되지 않는다는 점이다.

연결이 유지되지 않기 때문에 한번의 통신으로 하나의 결과만 얻을수있다.

항상 client에서 server로 요청을 한후에 필요한 정보를 얻어간다.

server가 자발적으로 client에게 정보를 전달할수 없다.

이러한 특징 때문에 실시간 처리가 어려워진다.

이전에 웹에서 실시간 처리를 하기 위해서 사용한 방법은 3가지이다.

polling, Long polling, streaming 방식이다.

## polling
client에서 주기적으로 server에게 변경사항이 없는지 확인하는 방법이다.

쉽게 Ajax로 구현이 가능한데, 가장 쉬운 예시로는 1초에 한번씩 server로 request를 보내 변화된 정보를 얻어오는 방법이다.

변동사항이 없어도 request를 요청한다. 

매우 비 효율적인 방법이다.

## Long polling
polling을 보완한 방법이다.

polling은 한번의 request을 보내고 response을 바로 받아오는 방식이다.

하지만 Long polling은 request을 보내면 어떤 이벤트가 발생되기 전까지 response를 보내주지 않는 기법이다.

polling방식에 비해 조금은 효율적이지만, response를 받게 된다면 다시 client에서 response를 보내야한다.

## streaming
streaming방식은 client의 request를 받은 server는 response대신에 헤더로 응답하는 구조이다.

헤더로 계속해서 응답을 하기 때문에 헤더에 대한 정확한 이해가 필요하다.

### 문제점
이 3가지 방법의 가장 큰 문제점은 바로 client에서 일방적으로 요청을 해야한다는 점이다.

양방향 처리같은 효과를 보여주지만 완전한 양방향 처리는 아닌셈이다.

웹소켓은 이러한 문제를 보완한 새로운 protocol이다.

## webSocket 동작 과정
* webSocket이 connection되는 url로 HTTP 요청을 보낸다.

* 이때 handShake가 이루어지고 HTTP 상태코드 101을 보내고 protocol을 upgrade한다.

* handShake를 통해 프로토콜이 upgrade되고 이때 사용한 TCP를 끊지않고 이 TCP를 통해 server와 client가 자유롭게 데이터를 전송한다.

## 장점
1. 실시간 처리를 구현할수 있다.

2. 기존 HTTP의 환경을 그대로 사용할수있기 때문에 http보안도 그대로 사용이 가능하며, 방화벽의 경우도 따로 설정이 필요하지 않다.(CORS도 동일하게 적용 가능)

## 단점
1. connection 유지는 server에 부하가 걸린다.(이론적으로는 connection의 갯수는 port의 갯수인 65000개가 가능하다.   )

2. 보안적인 문제점은 아직 유효하다.

3. 지원하지 않는 웹 브라우저가 존재한다.(IE는 10버전 부터 지원한다. Opera는 WebSoket을 지원하지 않는다.)
    * 이 문제점은 client단에서 sockJS를 이용하면 어느정도 커버가 가능하다.(나도 SockJS를 사용)
    
  