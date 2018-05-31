# Repliacation
DB 이중화이다.

DB 서버를 여러대를 만들고 쿼리를 분산시켜 DB서버의 부하를 줄이는 방법이다.

master - slave구조이며 

master는 write만 담당하며

slave는 read만 담당한다.

L4와 비슷하게 

master 밑에 여러개의 slave가 붙어있다.

master에서 데이터 변경이 일어난다면 그 데이터들을 slave에 반영

서로가 각각의 역할만 담당한다는 장점과 부하를 분산한다는 장점은 있지만

데이터의 유실과 일관성을 어떻게 유지할지는 조금 더 공부해야한다.