# Unicast
1 대 1로 통신하는 방식이다.

특정 주소하나만으로 통신하는 방법이다.

어떤 한 PC가 Unicast Frame을 전송하게되면 같은 네트워크상에 있는 모든 PC들은 이 Frame을 받아들여

자신의 MAC Address와 비교하게된다. 만약 자신의 MAC address와 전송받은 MAC Address와 다르다면 바로

Frame을 버려버린다. 이런 과정을 거치니까 PC의 CPU의 성능을 저하시키는 일은 일어나지 않게된다.

# Broadcast
로컬 랜상에 붙어있는 모든 네트워킁 장비들에게 통신을 보내는 방법이다.

로컬랜이란? 라우터를 의해서 구분지어지는 공간이다.

Broadcast는 어떤 특정한 네트워크의 장비가 아니라 내가 속한 네트워크 장비들과 통신하기 위해서 사용하는 방법이다.

Broadcast는 주소가 미리 정해져있다. 이 주소로 통신이 오게되면은 랜카드는 무조건 자신의 MAC Address와 일치하지 않아도

이 패킷을 CPU에게 전송한다. CPU는 이 패킷을 알아서 처리하게된다.

당연히 Unicast보다 CPU에 부담이 되게된다.

그렇다면 Broadcast는 언제 사용될까?

만약 두 PC간의 통신이 처음 일어나는 것이라면 MAC Address를 알고있을수가 없다.

그렇다면 다른 PC의 MAC Address를 알아내기위해하는 과정이 ARP이다. ARP가 바로 Broadcast이다.

이외에도 라우터끼리 정보를 공유할때나 다른 라우터를 찾을때에도 Broadcast가 일어난다.

Broadcast는 한번 일어나고 끝이 아니라 30초나 1분에 한번씩 일어난다.

# Multicast
라우터나 스위치에서 이 기능을 지원해주어야지 사용가능하다.

Multicast는 Unicast와 Broadcast와는 다르게 특정 그룹에 일괄적으로 데이터를 전송하는 방법이다.

Unicast와 Broadcast의 장점을 모두 결합했지만 라우터나 스위치에서 기능을 지원하지 않으면 사용불가능하다.