# RestFul API

## REST
HTTP 통신으로 데이터와 자료의 상태 정보를 클라이언트와 서버가 주고받는것

서버와 클라이언트를 분리시켜 단순화시키고 확장을 용이하게 할수있습니다.

또한 설계의 중심에 resource를 놓고 HttpMethod를 이용하여 resource에 접근합니다.

보통 REST API라 하면은 JSON이라고 생각을 하는데 이것은 dataFormat 일뿐 JSON이 REST API가 아니다.

### REST의 구성요소
- Resource(자원) : 처리되는 대상을 Resource라고 지칭한다. URI로 표현된다.
- Method(행위) : 어떠한 자원이라도 일관되게 행위가 정의된다. HTTP Method인 GET,POST,PUT,DELETE로 행위가 결정된다.
- Representation(표현) : HTTP Method와 URI만으로는 모든 내용을 표현할수 없다. 이때 정보부분을 표현하는것이 HTTP Body이다.
### REST의 특징

- Uniform Interface : 리소스에 종류에 상관없이 동일한 API를 가진다. 이미지 처리나 문서 처리도 같은 API를 통해 이루어진다.
- 독립적인 클라이언트와 서버 : 서버와 클라이언트는 독립적으로 존재한다.
- 무상태(Stateless) : 요청간 클라이언트의 정보가 서버에 저장되어서는 안된다.
- 캐시가능(Cacheable) : HTTP 프로토콜을  사용하기 때문에 기존 웹 인프라를 그대로 사용가능하고, 브라우저에서 HTTP 캐시를 이용하는 등의 동작이 가능하다.
- 계층화(Layered System) : 클라이언트는 서버와 직접 연결되었는지, 중간서버를 통해 연결되어있는지 알수없다. 중간에 존재하는 서버를 생성해 보안이나 로드밸런싱등을 수행할수있어 확장에 용이하다.
- self-descriptiveness : 별도의 주석이나 문서가 없이도 REST API만 보고 쉽게 이해해야 한다.

## RESTFUL API란?
REST의 설계를 잘 지켜 만든 API를 RestFul API라고 지칭한다.
RESTFul API는 명확히 역할이 나누어져 있어야하며 분리되어야한다.

## 장점
1. 기존의 WEB 인프라를 그대로 사용하기 때문에 별다른 환경설정이 필요하지 않다.
2. REST API 메시지 자체를 읽기만해도 본래의 의도를 알수있기 때문에 사용이 쉽다.
3. client와 server가 명확히 분리된다.
4. 원하는 데이터 표현을 사용가능하다.(JSON,XML,YAML)

## 단점
1. 사용할수 있는 method가 4가지로 정해져있다.
2. 표준이 없어 관리가 힘들다.
3. REST API를 RDBMS에 사용하기 위해서는 적당한 구조를 만들기 힘들다 오히려 NoSql이 더욱 적당하다.