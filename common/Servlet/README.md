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