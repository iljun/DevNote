# XSS
공격하려는 사이트에 스크립트를 넣는 공격 기법이다.

만약 사이트에 스크립트를 넣는다면 사이트에 접속된 사용자는 삽입된 코드를 실행하게 되고

의도치 않은 요청이나 Cookie나 Session에 대한 민감한 정보를 탈취당할수있다.

주로 Session을 탈취하기 위한 목적으로 사용된다.

### 공격방법
```
1. <script>태그로 javaScript를 실행 
2. <a href=""/>로 javaScript를 실행
3. event속성으로 javaScript를 실행
```

### 방어법
```
1. 데이터를 입력할때와 출력할때 모두 Filter링을 하는 방법
2. 쿠키 생성시 '보안 쿠키'라는 파라미터를 지정하면 TLS 상에서만 사용하게 할 수 있으며, 
    'HTTP ONLY'라는 파라미터로 웹 브라우저상에서만 쓸 수 있게 할 수도 있다.
```