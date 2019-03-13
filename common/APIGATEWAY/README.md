# API Gate Way
API의 앞단에서 모든 서버들의 endpoint를 묶어 단일화하고 중복된 기능등을 하나로 묶는 기능을 담당한다.

또는 여러서버로 라우팅, 로드밸런싱, 인증 및 인가의 기능을 담당한다.

MSA를 적용하게 된다면 각각의 기능마다 서버가 존재한다.

하지만 client의 입장에서 각각의 서버를 호출해 모든 정보를 가져와 필요한 정보만 정제해 화면에 뿌려준다면 

한번의 API 호출이 아닌 여러번의 호출을 반복해야한다.

서버쪽에서 하나의 로직이 변경되었을때 Client는 로직이 변경된 부분을 직접 디버깅을 통해 찾아내고 직접 담당 팀과 커뮤니케이션을 통해 

로직을 변경해야한다.

이러한 문제점을 해결할수 있는것이 API Gate Way이다.

Client의 입장에서는 API Gate Way팀하고만 협업을 하거나 하나의 Endpoint만 알면 개발이 가능하다.

서로가 독립적이고 계층화되는 것이다.

## API Gate Way 주요 기능
1. 인증 및 인가
    * 하나의 Application에서 인증 및 인가를 담당하는 기능을 구현하는건 어렵지않다.
    하지만 여러개의 Application으로 나누어진 서비스라면 반복된 인증패턴을 계속해서 구현해야한다.
    유지보수와 중복 소스코드가 엄청나게 늘어난다.
    이럴한 문제를 해결하기 위해 API Gate Way에서 인증 및 인가를 담당하게 된다.
    그렇다면 각각의 Application에서는 인증과 인가에 대한 신경을 쓰지않고 비지니스로직에만 신경쓸수있게된다.
    
2. API 호출
    * API Gate Way의 주된 역할이다. API Gate Way를 통해 서비스에 접근하게 되면 API Gate Way는 API를 호출한다.
    단순히 API 호출만이 아니라 로드밸런싱이나 endpoint와 client에 따라 같은 url이지만 다른 API를 호출할수도 있다.
    같은 ```/api/post```이자만 Admin은 ```/api/post/admin``` user는 ```/api/post/user```식으로 바꾸어 호출가능하다.
    
3. 프로토콜 변환
    * API가 웹브라우저와 직접 요청을 주고받는 형태가 아니기 때문에 http이외의 프로토콜을 사용해도 API Gate Way에서 변경이 가능하다.
    호출하는 입장에서는 항상 같은 프로토콜을 사용할 필요가 없다.
    예를들어 일반적인 경우에는 Rest로 호출하지만 IOT같은 Rest도 무거운 상황의 Client라면 다른 프로토콜을 이용해 요청이 가능하다.