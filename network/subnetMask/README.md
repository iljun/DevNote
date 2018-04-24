# Subnet Mask
주어진 IP를 네트워크 환경에 맞게 나누는것

IP주소를 가지고 어디까지가 네트워크 부분이고 어디까지가 호스트부분인지 나타내는 역할

만약 IP를 나누지 않는다면 브로드캐스트가 과도하게 발생하게된다.

즉 Subnet Mask는 주어진 IP를 적절히 나누어 과도한 브로드캐스트를 방지하는 방법.

또한 Subnet Mask로 IP주소를 나누게되면은 라우터로 통신을 해야한다.

### Default Subnet Mask
주어진 IP를 나누지 않고 그대로 사용하는 경우이다.

A class의 default Subnet Mask : 255.0.0.0

B class의 default Subnet Mask : 255.255.0.0

C class의 default Subnet Mask : 255.255.255.0
