# index
index란 RDBMS에서 검색의 효율을 높이기 위한 하나의 기술입니다.

index가 설정되어있는 테이블의 경우 index를 사용하여 검색을 진행했을때
Table을 fullScan하지 않고 색인화 되어있는 index파일을 검색해 검색속도를 빠르게합니다.

## index는 B-Tree 구조로 색인화되어있습니다.

### index를 사용하면 DML의 경우 비효율적입니다.
insert,update,delete를 실행할 경우 index를 구성하고 있는 B-Tree를 재구성해야 하기 때문입니다.

B-Tree를 사용하는 이유는 일관된 검색속도를 유지하기 위해서.
Tree의 검색 효율은 높이에 따라 좌우되는데 B-Tree는 balance Tree이기 때문에 일정하고 빠른 속도를 유지할수있다.

데이터베이스의 성능에서 가장 중요한 부분중 하나가 어떻게 디스크 I/O을 줄이느냐가 관건이다.

B-Tree의 하나의 블락에 크기가 한번에 디스크에서 I/O을 할수있는 크기라면 어떠한 데이터든 일정한 시간내에 조회할수 있는 장점이생긴다.

이러한 장점 때문에 B-Tree를 사용하는것이다.

### Index검증 방법
mySql Workbench기준

작성한 쿼리문 앞에 explain 키워드를 붙이면 여러가지 정보를 반환해주는데
이때 type을 보게되면은 index를 활용하는지 PullScan을 하고있는지 정보를 알수있다.