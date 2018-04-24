#Broswer Operation process

1. Browser에 url을 입력

2. DHCP로 자신의 IP주소와 가장 가까운 라우터의 IP주소, DNS서버의 IP주소를 받는다.

3. ARP를 이용해 가장 가까운 라우터의 MAC주소를 알아낸다.

4. Browser는 DNS에 ip주소를 요청
   
   * DNS Server가 ip 주소를 반환하는 과정 ex)www.naver.com
        * Host는 DNS server에 DNS Query를 질의
        * DNS Server는 Root NameServer에 .com부분에 해당하는 질의
        * .com nameServer에 다시 질의를 보내면 naver.com에 대한 ip주소를 반환
        * naver.com naverServer에 다시 질의를 한다면 www.naver.com에 대한 ip주소를 반환
   * DNS Server또한 계층화 되어있기 때문에 여러번 질의를 반복한다.
   
5. Browser는 IP주소를 기반으로 해당 웹서버가 존재하는 서버와 통신 
    (IP주소로 연결되는 방법 추후 추가)
<!-- 
    TODO IP주소로만 연결되는 방법 정확히 찾기 --> 라우터끼리 연결이 되서 데이터를 보내는듯
-->

6. IP주소르 알아낸후 Http Request를 위해, 3 way handShake가 일어나고 서로간의 데이터 교환이 끝난후 
    
    4 way handShake가 일어나고 통신이 끝기게 된다.
    
7. Browser는 Http Reponse에 들어있는 html을 렌더시켜 화면에 그려준다.

### 용어 정리    
```
    * DNS(Domain Name System) : Host의 도메인 이름을 네트워크 주소로 변환하거나 그 반대 역할을 하는 서버
    * DHCP(Dynamic Host Configuration Protocol) : Host의 IP주소 및 TCP/IP의 설정을 클라이언트에게 자동으로 제공하는 프로토콜
    * ARP(Address Resolution Protocol) : 네트워크 상에서 IP 주소를 물리적 네트워크 주소로 대응시키기 위해 사용되는 프로토콜이다
                                            IP주소를 이용해 같은 네트워크에 존재하는 Host들의 IP와 MAC Address를 알아내는 프로토콜
    * DNS Query : IP주소로 domain Name을 변환
```