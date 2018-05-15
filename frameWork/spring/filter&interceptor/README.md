# Filter & Interceptor & AOP

3가지 모두 하는일은 비슷하지만 절대적으로 호출되는 시점이 다르다.

우선 filter와 interceptor는 servlet에서 호출하는 개념이며 

AOP는 코드 내부에서 작동한다.

servlet을 중심으로 filter는 servlet이전의 요청과 servlet을 통해 나가는 응답에 대해 

모든 요청을 가로챈다.

interceptor는 servlet을 거치고 들어오는 요청과 servlet으로 나가는 요청을 가로채 어떠한 작업을 실행한다.

AOP는 filter - servelt - interceptor를 지나 코드 내부에서 작동하는 개념이다.

실제 filter는 web.xml에 작성하며 interceptor는 spring-servlet설정에 추가한다.

filter는 주로 인코딩이나 보안 관련 처리같은 전역 처리에 좀 더 알맞은것 같으며

interceptor는 조금 더 디테일한 인증,권한 처리등에서 주로 사용한다.