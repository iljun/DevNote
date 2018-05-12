# Http Method

## GET
Client가 Server로 정보를 요청할때 사용한다.

요청 Parameter는 QueryString을 통해 전송된다.

## POST
Client가 Server로 정보를 전송할때 사용한다.

전송 데이터는 Http Body에 담겨 전송되게 된다.

## PUT
Client가 어떠한 정보를 수정할때 사용한다.

전송데이터는 마찬가지로 Http Body에 담겨 전송되게 된다.

## DELETE
Server의 데이터를 삭제할때 사용된다.

## HEAD
GET과 유사한 방식이지만 httpHeader이외에는 아무 정보도 보내지 않는다.

서버의 다운 여부나 웹서버의 정보를 얻기위해 사용한다.

## OPTIONS
서버에서 지원하는 메소드의 종류를 알수있다.