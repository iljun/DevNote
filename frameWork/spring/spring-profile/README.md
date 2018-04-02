# spring-profile
로컬, 개발 서버, 운영 서버등 여러 곳에서 같은 Application을 실행할 때 몇가지 속성을 바꿔주고 싶을때 사용한다.

로컬, 개발 서버, 운영 서버에서 사용하는 DB가 전부 다를 수있다.
이때 배포마다 내부 설정을 변경할 필요없이 Spring-profile을 이용하면 상황에 맞게 설정 변경이 가능하다.

Spring-boot에서는 application.properties나 application.yml을 사용해 지정할수있다.

일반적인 spring-framework에서는 web.xml에 설정이 가능하다.

jar파일 실행시 JVM Option 및 application.properties의 설정에서 어느 profile을 실행할지 설정 가능하며

Web.xml에서 간단히 어떠한 profile을 사용할것인지 명시해주면 내부 설정을 맞게 변경된다.