# OSI 7 Layer

| Layer |   PDU |   프로토콜    |   기능  |
|   --  |   --  |   --  |   --  |
|   Application Layer <br/>(응용 계층)    |   Data    |   Http, FTD, DNS, DHCP, SMTP, NFP, RTSP   |   사용자가 네트워크에 접근할수 있게하는 계충 |
|   Presetation Layer <br/>(표현 계층)   |   Data    |   JPEG, MPEG, SMB, AFP    |   데이터를 하나의 표현 형태로 변환하는 계층, 수신받는쪽과 발신하는쪽의 전송데이터를 서로 이해할수 있는 데이터로 변환하는 계층   |
|   Session Layer <br/>(세션 계층)   |   Data    |   SSH, TLS, ISO8327, Apple talk, NetBIOS  |   통신장치간의 상호작용을 설정하고 유지하고 동기화한다. <br/>통신을 연결하고 관리하는 계층  |
|   Transport Layer <br/>(전송 계층) |   Segments    |   TCP, UDP, ARP, RTP, SCTP, SPX   |   패킷들의 전송이 유효한지 판단하고, 실패한 패킷은 재전송하는 등 신뢰성있는 통신을 보장하는 계층   |
|   Network Layer <br/>(네트워크 계층) |   Packets |   IP, ICMP, IGMP, RIP, IPX, DDP   |   패킷을 발신지로부터 목적지까지 전달하는 공간이며 전송 경로를 설정한다. <br/>패킷이 정상적으로 전달되도록 보장하는 계층 |
|   Data Link <br/>(데이터 링크)  |   Frames  |   MAC, PPP, 무선랜   |   한 장치에서 다른 장치로 프레임을 전달하는 역할을 담당한다.   |
|   Physical Link <br/>(물리적 링크)  |   Bits    |   Ethernet, RS-232C, Moderm   |   통신케이블로 전기적 신호를 전송하는 역할  |

## 작동
전송시 7계층부터 1계층까지 각각의 인식할수 있는 헤더를 붙이고 (캡슐화)
수신시 1계층부터 7계층까지 헤더를 뗴어낸다 (디캡슐화)

### 용어
```
    * PDU : 각 레이어가 처리하는 데이터 단위 

```