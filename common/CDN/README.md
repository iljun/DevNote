# CDN
클라이언트와 콘텐츠 서버와의 중계자 역할.

만약 CDN을 사용하지 않으면 클라이언트는 일일이 콘텐츠 서버에 접속해야하며 콘텐츠 서버는 일일이 응답해야한다.

이것은 엄청난 트래픽이 발생하고 성능에 매우 취약하며, 거리가 먼 콘텐츠서버에 접속하는 경우 속도가 느려지게된다.

CDN은 콘텐츠 서버를 대신하여 client와 가까운 물리적 위치 및 네트워크에서 client의 요청에 응답하는 방식입니다.

대부분의 CDN은 콘텐츠에 대한 요청이 발생하면 최적으로 배치된 CDN서버에 client가 위치하게 되며 해당 서버는 캐싱된 버전으로 응답하게 된다.

만약 CDN이 원하는 버전을 찾지 못했을 경우 다른 서버에서 콘텐츠를 찾은 다음 client에게 response하게 된다.

## 작동과정
1. client는 url을 요청
2. DNS에서 url을 검색
3. CDN서버이면 서버에 접속해 캐싱된 결과물을 return

## 캐싱 방식의 종류
* static caching
    * 사용자의 요청이 없어도 origin Server의 Content를 미리 복사한다.
    * 사용자가 CDN Server에 접속하여 Content를 요청하면 origin Server에 존재하는 모든 Content는 Cache Server에 존재한다.


* Dynamic caching
    * 최초 Cache Server에는 Content가 없다.
    * client의 요청이 들어오면 Content를 확인하고 존재하지 않는다면 Origin Server에 요청한다.
    * 각 Content는 일정 시간이 지나면 Cache Server에서 삭제될수 있으며, Origin Server를 통해 Content를 유지할것인지에 대한 판단도 가능하다.

## CDN의 이점
1. 성능
    - Origin Server에 접속하여 Content를 가져오는것보다 빠르다.
2. 가용성
    - 트래픽 급증이나 잠재적인 서버 중단같은 경우에 대응이 가능하다.
