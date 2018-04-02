# RestTemplate
Spring에서 지원하는 Http 요청이 가능하게 하는 객체이다.

이전 HttpClient를 사용해 요청하던 Http요청을 간단하게 구현할수 있다.

반복적인 코드를 줄이고 가독성을 높일수있다.

또한 Http 요청 결과를 객체 형식으로 매핑 가능하며,
다양한 Http header설정을 추가할수 있다.

## restTemplate 설정
xml이나 생성자를 통해 restTemplate 객체 설정이 가능하다.
connection Timeout, readTimeOut등이 가능하며,
기본적으로 HttpMessageConverter가 들어있다.