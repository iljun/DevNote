# SpringBoot Feature
* Web Developer
    - Web Application을 만들기에 적합하고, 내장 Tomcat이나 Jetty등을 이용해 HTTP서버를 쉽게 만들수있다.
 
* SpringApplication
    - main 메소드에서 SpringApplication을 실행하는 편리한 방법을 제공한다.
    
* Application events and listeners(추후 자료 추가)
    - 리스너를 추가하는 파일을 생성해 새로운 리스너를 추가할수있다. ```META-INF/```밑에 파일을 설정한다.
    - 다양한 이벤트도 파일로 관리가 가능하다.
    
* Admin features
    - ```spring.application.admin.enabled```속성을 이용하여 관리자관련 기능을 편하게 설정 가능하다.
    - application을 원격으로 접근하고 관리하는데 유용하다.
    
* Externalized Configuration
    - YAML 파일을 사용해 설정을 외부화 시킬수있다.
    - 하나의 Application이 서로 다른 설정을 통해 실행될수 있다.
    
* Properties Files
    - properties 파일을 이용해 공통적인 설정 및 다양한 설정을 관리할수있다.
    
* YAML Support
    - 계층적 설정을 지원한다.
   
* Type-safe Configuration
    - Type-safe Configuration으로 application의 설정의 validation을 강력하게 지원한다.
    
* Logging
    - 공통 로깅을 제공한다.
    - 로깅 종속성은 기본으로 관리되고, 사용자 지정이 필요하지 않은 경우 종속성 변경을 하면 안된다.
    