# Session & Cookie

## Session
사용자가 웹브라우저를 통해 웹서버의 접속한 시점부터 웹브라우저를 종료하기 전까지 필요한 정보를 저장하거나 어떠한 상태를 유지시키기 위한 공간

사용자의 정보는 서버의 메모리에 저장된다

#### session의 동작과정
 * 브라우저가 서버에 request를 전달
 * 서버는 request-header 의 필드인 cookie를 통해 session-id를 검색
 * session-id가 존재하지 않으면 session을 생성해 response-header에 session-id를 추가하여 리턴
 * 브라우저가 종료되거나 session의 만료시간에 도달하지 않는이상 session-id를 통해 session에 접근한다.
 
## Cookie
cookie는 세션과 반대로 사용자의 하드에 데이터를 저장하는 방식.

만료시간을 과거로 설정하면 쿠키는 저장되지않고 바로바로 삭제된다.

session과 달리 영구적으로 저장할수 있으며 보안성이 낮다. 

## local Storage
Cookie와 마찬가지로 사용자의 하드에 데이터를 저장하는 방식이다.

### Cookie vs localStorage
사용자의 정보를 사용자의 하드에 저장한다는 점은 똑같지만 둘은 용도가 다르다.

쿠키는 서버롸 클라이언트 측에서 데이터를 사용하기 위한 저장소이고 

localStorage는 클라이언트 측에서만 동작한다.

데이터를 서버와 클라이언트가 같이 사용해야한다면 쿠키가 사용용도가 적당하며

클라이언트만 데이터를 사용한다면 localStorage가 적절하다.