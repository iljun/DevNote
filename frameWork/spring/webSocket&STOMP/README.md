# WebSocket + STOMP
Spring에서는 WebSocket을 지원한다.

순수한 webSocket을 지원하지만 WebSocket + STOMP sub Protocol을 권장한다.

## 장점
* STOMP 규격에 맞는 모든 Message Broker를 적용할수있다.
    * STOMP로 규격을 맞추었기 때문에 다양한 Client를 모두 적용이 가능하다. RabbitMQ, Kafaka등의 Message Queue도 적용이 가능하다.

* STOMP Frame을 보고서 어떠한 Message인지 판별이 가능하다.
    * CONNECT, SEND, MESSAGE, SUBSCRIBE, UNSUBSCRIBE, DISCONNECT, HEARTBAET 등 상황에 맞는 Message를 표현이 가능하고 추가적으로 헤더를 붙일수 있다.
    * 추가적인 헤더로 Token기반의 인증방식을 적용 가능하다.
        * SockJS로 브라우저단에서 브라우저 호환성을 높였지만 SockJS의 이슈중 하나인 webSocket HandShake할때 Custom Header를 추가하지 못하는 이슈가있다.
        handShake때 인증을 진행하지 못했기 때문에 나는 STOMP Connection할때 인증토큰을 이용해 인증문제를 해결했다.
## 이슈
* WebSocket은 모든 브라우저가 지원하지 않는다. 이러한 문제점에 대한 해결책은 SockJS를 적용하면 해결이 가능하다.

* 메모리관리가 중요하다.
    * 내부적으로 ConcurrentHashMap의 형태로 사용자의 정보를 저장하고있다.
    * 하지만 Client가 비정상적인 종료를 하게된다면 메모리에 사용자 정보를 계속 유지하게 된다. 사용자의 정보를 계속 유지한다면 여러가지 예외상황이나 트래픽이 많은 상황에서 Out of Memory이슈가 발생한다.
    * 이런 점을 해결하기 위해서는 주기적으로 server와 client에서 서로가 연결되어있는지 확인이 필요하다.
    * 이 문제를 해결하기 위한 방법이 HEART BEAT이다. 주기적으로 서로간의 신호를보내 정상적인 연결이 살아있는지 확인하는 작업이다.
    

### Spring이나 Socket.io를 사용한다면 개발자의 입장에서 Message Handler정도만 구현하면 되기 때문에 간편하게 개발이 가능하다.
### 하지만 실제로 서비스하려면 메모리정보나 scale out을 했을때 Message Queue의 성능과 Connection관리등 신경써야할 부분이 상당히 많다.