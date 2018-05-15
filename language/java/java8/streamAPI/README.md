# streamAPI
Collections을 처리할때 각 요소를 반복하면서 직접처리해야 했다.

이러한 불편함을 해결하기 위한것이 StreamAPI이다.

StreamAPI를 이용하면 멀티스레드 코드를 구현하지 않아도 병렬처리 가능하다.(parallel 키워드)

StreamAPI는 3가지 단계로 구성된다.

1. 스트림 생성
2. 중계 연산 
3. 최종 연산 

최종 연산 이후에는 해당 스트림을 다시 사용할수 없다.

### Collection과 Stream의 차이점은???
Collection은 자료구조의 구현체이고 Stream의 자료구조를 다루는 역할이다.