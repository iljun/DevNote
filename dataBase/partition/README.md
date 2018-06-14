# Partition
물리적인 용량 한계를 극복하기 위해서 여러대의 데이터베이스에 나누어 저장하는 방식 

샤딩은 물리적으로 다른 데이터베이스에 데이터를 수평분할 방식으로 분산 저장하고 조회하는 방법을 의미한다.

여러 데이터베이스를 대상으로 작업해야 하기 떄문에 경우에따라서 JOIN 연산등의 제약이 생길수 있다.

예전에 샤딩은 애플리케이션 서버 레벨에서 구현했지만 최근에는 플랫폼 차원에서 제공하려는 시도가 많다.

Hibernate Shards나 CUBRID SHARD, Spock Proxy, GIzzard는 애플리케이션 서버에서 작동하는 방식이며 
 
nStore, MongoDB는 데이터베이스 자체에서 샤딩기능을 제공하기도 한다.

## 수직분할(Vertial Partitioning)
하나의 테이블을 쪼개서 따로 저장하는 방식이다.

원래 하나의 테이블을 나누어 다른 DB에 저장하는 방식이다.


## 수평분할(Horizontal Partitioning) == sharding
연속된 key값이 아닌 특정한 category와 같은 종류에 따라 데이터를 수평으로 분리하는것 

국가별로 나눈다면 한국,미국,중국으로 나눌수 있다.

샤딩은 바로 수평분할을 가리키는 말이다.

원래 하나의 스키마를 복제해 여러개로 만들고 

특정한 key값을 기준으로 다른 스키마에 저장하는 방식이다.

#### 한계
###### range-based sharding
특정 ID값을 기준으로 ID범위에 따라 샤드를 나누는 방식이다.

ID값이 증가하는 추이를 보고서 새로운 샤드 추가가 쉽다는 장점이 있지만,

디스크 사용량이나 쿼리 처리량의 밸런스가 많이 안맞는 경우가 발생하기도 한다.

###### modulus-based sharding
id값 % 샤드 갯수 의 결과값으로 샤드 위치를 결정하는 방법이다.

Range방식에 비해 사용 밸런스는 잘 맞지만 이 방식은 샤드 추가가 어렵다.

샤드를 확장할시 기존의 각 샤드마다 데이터의 재배치가 필요하다.