# sql Injection
Java에서는 JDBC를 이용해 데이터베이스로 쿼리문을 사용할수 있는 interface가 2개 존재한다.

Statement 와 PreparedStatement이다.

## statement & prepared statement
두가지의 가장 큰 차이점은 캐시 사용여부이다.

statement는 캐시를 사용하지 않고, prepared statement는 캐시를 사용한다.

쿼리를 실행하는 과정은 
1. 쿼리 문장 분석
2. 컴파일
3. 실행
순서이다.

statement는 1~3까지의 과정을 매번 쿼리를 실행할때 마다 과정을 거친다.

매번 쿼리실행의 경우 비효율적이다.

하지만 prepared statement는 한번이라도 실행된 적이 있으면 캐싱을 하게된다.

매번 쿼리문을 실행할때 1~3 단계를 거치지 않아도 된다.

캐싱이 되어있기 때문

## sql Injection 방어법
PreparedStatement를 사용하는 방법이다.

Statement의 경우 정적인 쿼리문만 처리 가능하다.

쿼리문에 값이 미리 입력되어 있어야한다.

Statement가 DB에 전달하는 쿼리문은 단순한 string형태이다.

그렇다면 개발자가 sql Injection을 제대로 방어하지 않았다면 사용자가 악의적이 목적으로 쿼리문을 작성했을때

그 쿼리문자체를 데이터베이스에 전달하기 때문에 sql Injection이 발생되는 것이다.

그렇다면 PreparedStatement의 경우는 쿼리문이 캐싱이 되어있고

캐싱이 되어있기 때문에 매개변수 바인딩을 통해 쿼리문을 전달 가능하다.

이 의미는 쿼리문을 미리 작성해놓고 매개변수 바인딩을 통해 쿼리문을 완성하기 때문에 

대부분의 sql injection은 방어가 가능하다.

바인딩 데이터는 SQL 문법의 의미를 가질수 없다.

Statement는 단순한 String형으로 쿼리문이 전달되기 때문에 SQL 문법의 의미를 가질수 있지만,

PreparedStatement는 매개변수가 SQL문법의 의미를 가질수 없기 때문에 sql injection 방어가 가능하다.