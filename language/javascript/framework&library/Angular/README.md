# Angular
Google에서 만든 SPA(Single Page Application)방식의 프론트엔트 개발을 위한 framework이다.

사용 언어는 TypeScript와 ES6를 사용할수있다.

## 장점
1. 코드의 분리, 유지보수가 용이하다.
    Dependency Injection을 이용해 코드의 분리 및 재사용이 가능하다.
    서버와 통신을 하는 Service 클래스와 HTML,css,JavaScript가 한곳에 모여있는 Component 클래스가 명확히 구분되어있다.
   
2. 화면전환이 빠르다.
    일반적인 웹은 링크를 클릭할때마다 서버로부터 새로운 페이지를 요청받는데 
    Angular는 클라이언트 측에서 화면을 생성해내고, 필요한 부분만 Server를 호출하기 때문에 더욱 빠르다.

## 단점
1. 초기 로딩 속도가 느리다.

2. 검색엔진에 인덱스가 제대로 되지 않는다.
    구글은 Angular로 만든 홈페이지를 제대로 인덱싱 하지만, 다른 네이버, 다음에서는 모두 Angular로 만들어진 페이지를 제대로 인덱싱하지 못합니다.
    네이버나 다음에서 인덱싱이 제대로 되게 하려면 Angular Universial을 사용하던지 해야한다.