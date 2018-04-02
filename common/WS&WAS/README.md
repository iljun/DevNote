# WS & WAS

## WS(WebServer)
웹브라우저의 request를 받는 곳으로 작업의 결과를 브라우저에게 response를 응답하는 역할이다.

주로 정적인 처리에 적합하다.

html,css,image 등 정적인 파일을 관리할때 성능이 뛰어나다.

다양한 동적인 처리를 위해서 WAS와 통신하기도 한다.

정적인 처리 이외로 SSL설정이나 로드밸런싱 설정이 가능하다.

동작 프로세스
1. 정적 컨텐츠 요청시 --> WebServer에서 바로 response
2. 동적 컨텐츠 요청시 --> WAS로 Request를 넘겨주고 WAS의 Response를 받아 client로 Response

## WAS(Web Application Server)
정적인 처리 이외로 동적인 처리를 이곳에서 진행한다. 컨테이너, 웹컨테이너, 서블릿 컨테이너라고 불리기도한다.

DB와의 연동이나 프로그램으로 데이터 조작이 필요한 경우에 사용한다.

1. 웹서버에게 Reqeust를 전송받는다.
2. 컨테이너는 web.xml을 참조하여 해당 Servlet에 대한 Thread를 생하고 , httpServletRequest와 httpServletResponse를 생성하여 전달.
3. 컨테이너는 Servlet을 호출
4. 호출된 Servlet에서 작업 처리
5. 작업이 완료된 동적 결과물을 Response객체에 담아 컨테이너에게 전달
6. 컨테이너는 결과물을 HttpResponse형태로 변환해 WS에게 전달하고 생성이 되었던 Thread를 종료, httpServletRequest와 httpServletResponse를 소멸시킨다.
