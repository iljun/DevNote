# Sql Injection
클라이언트의 입력값을 조작하여 서버의 데이터베이스를 공격하는 방법이다.

사용자가 입력한 데이터를 필터링이나 이스케이프하지 못하면 발생할수 있다.

예를 들어 로그인 입력창이라고 가정을 했을때

id 와 password를 입력해야한다.

password 입력칸에 패스워드 이외로 ```or 1 = 1```

이라고 한다면 DB의 query문은 ```select * from user where id = AND password = 임의의값 OR 1 = 1``` 이라는 쿼리문을 생성할수 있다.

이러한 경우에는 password가 달라도 해당아이디로 로그인이 가능하게 된다.

또한 drop query문을 끼워넣어 전체 데이터 베이스를 날려버리는 경우도 존재한다.

## 방어법
XSS와 방어법이 겹치겠지만 sql injection 또한 유저에게 받은 입력값을 그대로 사용하지 않고 필터링과 escape을 실행해야한다.

필터링 이외로 prepared statement를 사용해 sql injection을 방어해야한다.
