# LAN(Local Area Network)
어느 한정된 공간에서 네트워크를 구성한것이다.

# WAN(Wide Area Network)
서로 떨어진곳을 네트워크로 연결한것이다.

인터넷은 대부분 WAN이다.

# Ethernet?
네트워킹의 한 방식이다.

TCP/IP를 사용하지 않고 CSMA/CD 프토콜을 사용하는 것이다.

우리나라의 90% 정도는 Ethernet방식을 사용한다.

### CSMA/CD (Carrier Sense Multiple Access/Collision Detection)
Ethernet에서 통신을 하려면 지금 네트워크 자원이 사용중인지를 먼저 판단해야한다.

만약 네트워크 자원이 사용중이 아니라면 바로 네트워크에 자원을 실어 보내는 방법이다.

네트워크의 자원이 사용중인지 아닌지를 판별하는것이 Carrier Sense이다.

그렇다면 만약 네트워크의 자원이 사용중이 아닐때 동시의 두개의 장비가 네트워크에 자원을 실어보낸다면?
이것을 Multiple Access라고한다.

두개의 장비가 네트워크에 동시에 자원을 실어보낼때 충돌이 일어난다면 이것을 Collision이라고 한다.

Ethernet은 Collision이 일어나지 않게하기 위해 점검을 하는데 이것을 Collision Detection이라고 한다.

하지만 만약 Collision이 발생하게 된다면 데이터를 전송하려는 장비는 랜덤한 시간동안 대기 후 다시 데이터를 전송한다.

만약 이러한 행위가 15번이 일어난다면 통신이 실패했다고 한다.

# TokenRing
Ethernet과 다른 방식으로 Token이란것을 소유하고 있을때만 네트워크로 데이터를 전송가능하다.

TokenRing의 특징을 Collision이 일어나지 않는다는 점이다.

TokenRing의 작동방식은 네트워크로 묶여있는 장비들이 Token을 소유할때 보낼 데이터가있으면 데이터를 전송하고 다른 장비로 

Token을 넘기는 행위를 반복함으로써 데이터를 전송하는 방법이다.