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

## EntityManagerFactory
주 목적은 EntityManager를 관리하는 역할이다.

EntityManagerFactory가 생성한 EntityManager들은 같은 DataBase에 접속하게 된다.

EntityMangerFactory는 한번 생성후 어플리케이션에 공유된다.

멀티쓰레드로 절대 공유하면 안된다.

## EntityManger
Entity를 저장,수정,삭제,조회 등 Entity를 관리한다.

## PersistenceContext
Application과 데이터베이스 사이에서 논리적인 개념으로 엔티티를 저장하는 환경
   
EntityManger를 이용해 접근이 가능하다.

EntityManger가 PersistenceContext에 Entity를 저장한다.

* 장점
    * 1차 캐시 : 엔티티조회시 PersistenceContext에 존재한다면 DB를 거치지 않고 바로 리턴
    * 동일성 보장 : 조회시 같은 엔티티는 같은 인스턴스를 리턴
    * 트랜잭션이 커밋되기 전까지는 내부 쿼리 저장소에 모아놓았다가 커밋되면 쿼리문을 전송한다.
    * 엔티티의 스냅샷을 유지하면서 변경사항이 있음을 감지, 엔티티가 최초 등록되었을때 Snapshot을 생성하고 flush시점에 엔티티의 변경사항을 참조해 자동으로 update
    * 지연로딩 : 연관된 엔티티를 모둡 불러오는것이 아니라 필요시에만 불러온다.