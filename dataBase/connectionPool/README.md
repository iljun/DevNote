# Connection Pool
사용자가 쿼리를 실행할때 마다 DB에 연결하고 쿼리 결과를 받아온다음 연결을 끊는 식으로 작동된다면 해당 서버의 cpu 점유율은 엄청나게 높아질수있다.

이러한 비 효율적인 문제를 해결하기 위해서 사용하는게 DB Connection pool이다.

Connection Pool은 사용자 지정 갯수만큼 DB Connection을 만들어놓고 pool에 보관중이다가.

필요할때마다 사용하고 반납하는 개념이다.

spring DBCP의 설정들을 보면은 min-connection size와 max-connection size가 있을것이다.

이건 최소 몇개의 connection을 가지고 관리하며 최대 몇개까지 connection을 만들지에 대한 설정이다.

비용이 큰 connection을 미리 만들어 놓고 사용함으로 성능에 이점도 생각보다 크다.

만약 min size를 넘어서 더 많은 connection이 필요한 경우 WAS가 커넥션을 더 만들게 된다.