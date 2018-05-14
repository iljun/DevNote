# Servlet
클라이언트의 요청을 처리하고 그 결과를 반환하는 기능을 가진 Servlet클래스의 규칙을 지킨 자바 클래스

javax.servlet.http.HttpServlet 클래스를 상속하여 개발한다.

Servlet은 흔히 CGI(Common User Integerface)라고 불린다.

# Servlet Container
Servlet을 관리해주는 역할 Ex) Tomcat

Servlet의 생명주기를 관리하고 요청에따라 Thread를 생성

Client의 Request를 받아주고 Response를 보낼수 있도록 웹 서버와 소캣통신을 한다.


#### DD(Deployment Descripot) : 배포 서술자
웹 컨테이너에게 지금 접속한 URL 주소가 서블릿 요청임을 인식하고 그 서블렛 클래스가 어디에 위치하는지 서술하는 파일
Tomcat의 경우는 web.xml이다.

# Tomcat의 Thread
Tomcat은 servlet Container로 request가 들어올때마다 Thread를 생성하지 않는다.

Thread생성 비용이 생각보다 만만치 않기 때문에 미리 200개 정도의 Thread를 미리 생성해두고 돌려가며 쓴다.

나중에 sourceCode를 열어봐야겠다.

## WEb 클래스 로더
JVM과 마찬가지로 WAR를 로딩하는 클래스 로더가 존재한다.

JVM클래스 로더와 비슷하나 로딩 우선순위가 일반적인 상위 클래스 로더보다 WEB-INF/classes와 WEB-INF/lib 디렉토리를 우선적으로 

로딩할 수 있도록 할 수 있다.