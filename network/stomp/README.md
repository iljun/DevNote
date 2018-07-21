# Stomp sub protocol
단순한 텍스트 기반의 스트리밍 메시지 프로토콜이다.

나는 webSocket과 stomp 프로토콜을 같이 사용했다.

stomp 프로토콜을 사용한 이유는 확장성이다.

webSocket은 html5의 기술이다.

mobile client가 대상이 아니다.

만약 web Client만 지원하다가 mobile클라이언트를 지원해야 한다면

새로운 messgae를 전달하는 코드를 추가해야 한다.

이런 작업은 불편한 작업이고 하기 싫다.

하지만 Stomp 프로토콜을 적용한다면 프로토콜의 규격이 생기고,

server는 Stomp 프로토콜의 규격으로 실시간 처리를 담당하고,

Web Client는 stomp + SockJS로 대응

mobile Client는 stomp에 관련한 라이브러리를 적용한다면

하나의 message Handler로 모든 clientㄱ 사용 가능하다.