# 3 way-handShake

TCP/IP 프로토콜을 이용해 데이터 전송 전에 상대방의 컴퓨터와 세션을 수립하는 과정

 * Client -> Server : SYN
 * Server -> Client : SYN + ACK
 * Client -> Server : ACK
 
1단계 : Client가 Server에게 접속을 요청하는 SYN패킷을 전송, 이후 Client는 SYN+ACK응답을 기다리는 상태(SYN_SENT)로 변환

2단계 : Server는 SYN요청을 받고 요청을 수락한다는 ACK+SYN flag라 설정된 패킷 발송 이후 Server는 Client가 ACK 응답을 기다리는 상태(SYN_RECEVIED)로 변환 

3단계 : Client는 다시 서버에서 ACK요청을 보내고 Server는 Established상태로 변환후 서로 데이터를 주고 받는다.


# 4 way-handShake
세션을 종료하기 위한 과정

1단계 : Client가 세션을 종료하겠다는 FIN 플래그를 Server에 전송. 자신은 FIN_WAIT_1 상태로 대기한다.

2단계 : Server는 ACK 응답을 보내고 자신의 통신이 끝날때까지 TIME_WAIT 상태가 된다. ACK 응답을 받은 클라이언트는 FIN_WAIT_2 상태로 변화하고 대기한다.

3단계 : Server가 통신이 끝나면 연결이 종료되었다는 FIN 플래그를 Client에게 전송, 자신은 LAST_ACK 상태로 변한다.

4단계 : Client는 확인했다는 ACK응답을 Server로 전송

## 용어
```
    * SYN : synchronized sequence numbers ( 시퀀스 번호 동기화 )
    * ACK : acknowledgment (응답 유효 필드)
    * FIN : ( 보낸 사람으로부터 더 이상의 데이터는 없음 )
```  