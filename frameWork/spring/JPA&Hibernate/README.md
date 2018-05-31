# JPA & Hibernate

## JPA
JavaSE, JavaEE를 위한 영속성(Persistence)를 위한 표준 기술이다.
JPA는 ORM 표준기술로 Hibernate, OpenJPA 등등의 구현체가 존재하고 JPA는 표준 인터페이스이다.

## Hibernate
JPA의 구현체 중 하나이다.
myBatis와는 다르게 SQL문을 내장하고 있고, 메소드명을 통해 쿼리문을 수행한다.

Hibernate의 장점은 어노테이션이나 xml설정으로 객체관계를 매핑할수있다.

또 다른 장점으로는 DBMS의 변경이 있을시 내부 설정의 dialect의 설정을 변경하면 해당 DBMS의 자동으로 적용 가능하다.

### 장점
DBMS의 변경이나, Table의 변경에 유동적으로 대처할수있고, 변경이 쉽다.

### 단점
SQL에 대한 이해가 부족하면 성능문제, 원하지 않은 결과를 얻을수 있는 단점이 있다.
복잡한 쿼리문의 경우 QueryDSL 등의 새로운 framework를 사용해야한다.(Hibernate의 깊은 이해가 없으면)
또한 모든 데이터베이스를 다룰수 있도록 추상화를 제공하지만, 정말 모든 DBMS의 기능을 이용하는데 한계가 있기 때문에
제한적인 부분에서는 다른 인터페이스를 사용해야한다.

HQL, Criteria, Native SQL등이 제한적인 부분에서 사용하는 인터페이스이다.

