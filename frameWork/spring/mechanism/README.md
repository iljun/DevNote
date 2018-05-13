# Spring mechanism

1. Application이 실행되면 WAS에 의해 web.xml이 lodaing

2. web.xml의 설정을 참조해 ContextLoaderListener가 생성 ContextLoaderListener는 ApplicationContext를 생성하는 역할을 수행

ApplicationContext는 Spring의 각종 bean들을 관리하는 역할 

3. 생성된 ContextLoaderListener는 root-context.xml(applicationContext.xml)을 loading

4. root-context.xml(applicationContext.xml)에 등록되어있는 Spring Container가 구동된다. 

Spring Container는 개발자가 작성한 각종 객체들을 관리하는 역할이다.

Spring Container는 개발자가 작성한 각종 Bean들을 생성

5. 클라이언트로부터 request가 들어온다.

6. DispatcherServlet이 생성되고 클라이언트의 요청들을 가로채 HandlerMapping을 통해 등록된 컨트롤러를 찾고, ViewResolver를 통해 등록된 view를 찾고 리턴한다.

7. DispatcherServlet은 Servlet-context.xml을 loading한다.(Servlet-context.xml -> 서블릿관련 설정이다. ViewResovler가 여기에 속한다.)

8. SpringContainer가 구동되며 응답에 맞는 적절한 로직을 실행한다.

## Spring Container종류
### BeanFactory
스프링의 설정파일에 등록된 Bean객체를 생성하고 관리하는 역할을 한다. 가장 기본적인 역할만 제공

컨테이너가 구동될때 객체를 생성하는것이 아니라 클라이언트 요청에따라 객체를 생성한다.(Lazy Loading)

### ApplicationContext
BeanFactory를 확장한 컨테이너이다.

BeanFactory에서 지원하지 않는 기능인 다국어처리, 트랜잭션처리등 다양한 기능을 지원한다.

컨테이너가 구동되는 시점에 Bean객체를 바로 생성한다.