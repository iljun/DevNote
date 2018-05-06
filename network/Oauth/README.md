# OAuth

Oatuh기반의 서비스는 API호출시 HTTP 헤더에 Access Token을 포함한 상태로 전송한다.

서비스는 이 Access Token을 이용해 유요한 요청인지 판단하게된다.

Session을 사용하지 않고, Http 헤더에 Access Token을 이용해 사용자 인증을 하는 방식이다.

Session을 사용하지 않아 보안의 이점이 높아질것 같지만, Access Token을 탈취당한다면 마찬가지로 보안에 취약해진다.

## Oauth 1.0

HMAC을 이용한 암호화방식 하나만 지원한다.

## Authentication vs Authorization
인증과 인가의 차이이다.

인증은 등록된 사용자인지에 대한 여부이다.

인가는 인증된 사용자에대해 권한을 부여하는것이다.

### 용어
```
    * User : Service Provider에 계정을 가지고 있으면서, Consumer를 이용하려는 사용자
    * Service Provider : OAuth를 사용하는 OpenAPI를 제공하는 서비스
    * Consumer : OAuth 인증을 사용해 Service Provider의 기능을 사용하려는 애플리케이션이나 웹 서비스
    * Request Token : Consumer가 Service Provider에 접근해 권한을 인증받기 위해 사용하는 값
                        인증이 완료된후에는 Access Token으로 교환된다
    * Access Token : 인증 후 Consumer가 Service Provider에 접근하기 위한 키를 포함한 값
```

## 작동방법
1. Consumer 가 Service Provider에게 request Token을 요청
2. Service Provider는 Request Token을 발급
3. Consumer는 User를 Service Provider로 Redirect시킨다. 이때 사용자 인증을 실시한다.
4. 인증이 완료된 후 Service Provider는 User를 Consumer로 Redirect.
5. Consumer는 Service Provider에게 Access Token을 요청
6. Service Provider는 Access Token을 발급
7. 발급된 Access Token을 이용해 접근

### 단점
1. 웹어플리케이션이 아니면 사용하기 힘든 단점이있다.
2. Access Token을 발급받은 후 계속 사용가능 하기 떄문에 보안에 취약하다.

# Oauth 2.0
외부 서비스의 인증 및 권한부여를 관리하는 범용 프레임워크.

OAuth 1.0a의 signature 생성이 필요없다. signature를 생성하지 않고 SSL에 보안을 의존한다.

써드파티 어플리케이션인 client가 주를 이룬다.

OAuth 1.0a는 한가지 인증방식만 제공하지만 OAuth 2.0은 다양한 환경에 사용가능한 인증방식을 제공한다.

OAuth 2.0도 2-legged모델도 지원하기는하나 가장 기본은 3-legged 모델이다.
### 용어
```
    * Resource Owner : 사용자 
    * Resource server : API Server
    * Client(Application) : 써드파티 Application
    * Authorization Server : 인증서버 
        * Authorization Server 와 Resource Server는 같은 Server일 수도 있다.
```

### 중요 개념
```
    * AccessToken : API를 사용하는 사용자의 id와 password를 저장하지 않고 인증토큰으로 대처하는 방법, 필요한 기능(권한)만 제공
                    AccessToken은 유효기간을 지닌다. 이 기간을 짧게 설정하고 기간이 만료되면 refreshToken을 이용해 token이용시간을 연장한다.
    * RefreshToken : 클라이언트가 같은 access Token을 사용하게 되면 결국은 해킹의 위험이 높아진다.
                    accessToken의 만료기간을 가능한 짧게하고 만료가 되면은 refreshToekn으로 accessToken을 새로 갱신하는 방법.
    * scopr : client의 ㅅ\권한을 설정하기 위한 기능이다. 로그인시 여러개의 권한을 요청할때 scope=... 이러한식으로 넘겨준다.
```

##### Client
client는 기본적으로 Confidential Client, public Client로 나뉜다.
    * Confidential Client : 웹 서버가 API를 호출하는 경우 client증명서(client_secret)을 안전하게 보관할수 있는 client
    * Public Client : 브라우저기반 Application이나 모바일 Application같은 경우 client 증명서를 안전하게 보관할수없는 client를 의미 이러한 경우 보통 redirect_url을 이용한다.
    
##### GrantType
Authorization Code Grant와 Implicit Grant를 제외하고는 대부분 3-legged OAuth가 아니다.

1.Authorization Code Grant(권한코드 발급 방식) : 
웹서버에서 API를 호출하는 등의 시나리오에서 Confidentail Client가 사용하는 방법이다.
public Client의 종류인 브라우저기반 Application이나 모바일 Application의 경우 사용한다.
로그인시 Url의 parameter로 response_type=code를 넘겨준다.
    
2.Implicit Grant : 
Public Client인 브라우저 기반의 Application이나 모바일 Application에서 이 방식을 사용하면 된다. 
Client 증명서를 사용할 필요가 없으며 실제로 OAuth 2.0에서 가장 많이 사용되는 방식이다.
로그인시에 페이지 URL에 response_type=token 라고 넘긴다.

3.Password Credentials Grant : 
이 방식은 2-legged방식이다. Client에 id/password를 저장해놓고 사용하는 방식이다.
Client를 믿을수 없을때는 사용하기 부적합하다.
로그인시 POST로 grant_type=password라고 넘긴다.

4.Client Credentials Grant : 
application이 Confidential Client일떄 id와 secrect값을 사용해 인증하는 방식이다.
로그인시 POST로 grant_type=client_credentials라고 넘긴다.

## 작동 방법
1. client는 Resource Owner에게 권한을 요청한다.
2. Resource Owner는 다양한 client환경에 걸맞는 인증 및 권한 부여 방식을 제공한다.(GrantType)
3. client는 Authorization Server에게 인증 및 권한방식을 전송
4. Authorization Server는 Access Token을 발급
5. client는 발급받은 Access Token을 이용해 Resource Server에게 전송
6. Resource Server는 Access Token을 통해 정보를 전달 만약 만료기간이 다된 Token은 refreshToken으로 변경

## OAuth 2.0의 단점
1. OAuth 1.0a는 token과 함꼐 token비밀번호를 같이 받는데 OAuth2.0은 비밀번호가 없어져서 클라이언트를 구별하기가 힘들어졌다.
2. Signature기능을 없앴기 때문에 SSL에 의존함으로 SSL이 뚤린다면 더 위험하다.
3. Http 오버헤드가 너무 크다.

## JWT ( Json Web Token)
Http 오버헤드를 줄이기위해 사용자의 인증정보를 담아 둘수있도록 만든 토큰이다.

##### 구조
JWT는 .를 기준으로 3가지 부분으로 나뉘어있다.

각 부분은 JOSE 헤더, JSON Claim Set, Signature라고 부른다.

###### JOSE 헤더 
JWT 토큰을 어떻게 해석해야 하는지를 명시한 부분이다.

토큰의 타입과 암호화 알고리즘을 보통 적어놓는다.

###### JWT Claim Set
실제 토큰의 바디로 토큰에 포함할 내용을 넣는다.

JWT는 토큰을 디코딩해 바로 값을 확인할 수 있는 구조로 되어있어서 DB조회를 통하지 않고 사용자에 관한 정보를 바로 사용할수 있다.

JWT Claim Set에는 절대로 중요한 정보를 넣어두면 안된다.

누구든지 Claim Set을 열어볼수 있기 때문이다.

###### Signature
JOSE헤더와 JWT Claim Set은 암호화가 아니라 단순하게 문자열을 인코딩한것이다.

누구나 열어볼수 있다는 의미이다.

토큰을 사용할 경우 이 토큰을 다른 사용자가 위변조했는지의 여부를 판단하는 부분이 Signature다.

JWT는 JOSE 헤더와 JWT Claim Set을 각각 인코딩한다음 .로 이어붙인다. 

JOSE 헤더에 기술된 알고리즘으로 인코등을 하면 JWT 토큰의 signature를 만들게 된다.
