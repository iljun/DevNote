# CORS & SOP

## SOP (동일 출저 정책)
자바스크립트 엔진 표준 스팩이다. 
Ajax와 iframe으로 접근할때는 동일 출저에서만 접근이 가능하다는 정책이다.
동일출저는 프로토콜, 호스트명, 포트가 같은것을 의미한다.

## CORS
SOP정책을 우회해 다른 Origin의 자원을 접근할수 있게하는 방법이다.

#### 브라우저 설정 변경
브라우저의 옵션을 변경하는 방법이다. 옵션을 해제한 상황에서만 사용가능하다. 일종의 편법이다.
또는 크롬의 플러그인을 설치하는 방법이 있지만 이것도 물론 편법이다.

#### JSONP
웹브라우저에서 css,js 등의 파일은 SOP의 영향을 받지 않고 로딩이 가능하다.
이 점을 이용해 외부의 origin에서 js파일을 읽어오듯이 요청결과를 json으로 변환하는 방법이다.
리소스 파일은 GET방식으로만 읽어오는것이 가능하기 때문에 GET방식만 사용 가능하다.

#### proxy server
중간 서버인 proxy server를 생성해 중간 과정을 하나 더 놓는것.

#### Simple Request
Http Method로 GET,POST,HEAD만 사용하고
http 요청 함께 http 헤더에 대한 설정이 없어여한다.

#### PreFlight
다른 Http Method를 사용가능하며,
http 요청과 함께 http 헤더 설정이 가능하다.
이 방법은 요청서버의 response header에 Access-origin이 요청하는 origin과 일치해야 자원에 접근 가능하다.
서버의 Access-origin을 확인하기 위해서 브라우저가 options Method를 전송해 요청 권한이 있는지 판단한다.

#### request with credentials
기본적으로 ajax호출시 브라우저의 정보를 전송하지 않는다.
이 해결방법은 Http 쿠키와 Http Authentication을 전송해 허용된 Client라는 점을 알리는것이다.