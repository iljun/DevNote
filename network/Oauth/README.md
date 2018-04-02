# OAuth

Oatuh기반의 서비스는 API호출시 HTTP 헤더에 Access Token을 포함한 상태로 전송한다.

서비스는 이 Access Token을 이용해 유요한 요청인지 판단하게된다.

Session을 사용하지 않고, Http 헤더에 Access Token을 이용해 사용자 인증을 하는 방식이다.

Session을 사용하지 않아 보안의 이점이 높아질것 같지만, Access Token을 탈취당한다면 마찬가지로 보안에 취약해진다.

## Oauth 1.0

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

### 용어
```
    * Resource Owner : 사용자 정확하게는 서버 관리자이다.
        Ex) 페이스북 서버
    * Resource server : API Server 
        Ex) 페이스북 API Server
    * Client(Application) : API를 이용하려는 사용자(Application) 
        Ex) 페이스북 API를 이용하려는 사용자 및 Application
    * Authorization Server : 인증서버 
        Ex) 페이스북 인증 서버
        * Authorization Server 와 Resource Server는 같은 Server일 수도 있다.
```


## 작동 방법
1. client는 Resource Owner에게 권한을 요청한다.
2. Resource Owner는 다양한 client환경에 걸맞는 인증 및 권한 부여 방식을 제공한다.
3. client는 Authorization Server에게 인증 및 권한방식을 전송
4. Authorization Server는 Access Token을 발급
5. client는 발급받은 Access Token을 이용해 Resource Server에게 전송
6. Resource Server는 Access Token을 통해 정보를 전달 만약 만료기간이 다된 Token은 refreshToken으로 변경

이같은 문제점 때문에 Https를 적용해 사용하는 경우가 많다.

또 다른 단점은 Http의 오버헤드가 늘어난다는 점이다.

한번의 요청에도 인증서버에 요청을하고 Resouce서버에 요청하는 방식이기 때문에 Http 오버헤드가 늘어난다.

이러한 단점을 해결하기 위해 나온것이 JWT이다.

## JWT ( Json Web Token)
Http 오버헤드란 단점을 줄이기위해 사용자의 인증정보를 담아 둘수있도록 만든 토큰이다.

하지만 토큰을 변경한다면 보안에 취약한점은 동일하다. 

이 토큰에 대한 무결성을 보안하기 위해서 서명이나 HMAC을 사용해 단점을 보완할수있다.

//추후 추가예정