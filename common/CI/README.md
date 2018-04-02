# CI(Continuous Integration)
개발자들이 각각 개발한 코드를 모아서 한꺼번에 빌드하는 통합 과정을 특정한 시점이 아니라
주기적으로 실행해 통합에서 발생하는 오류를 사전에 해결하고 시간을 단축시키는 기법이다.

## CI의 핵심 요소

### CI Server
빌드 프로세스를 관리하는 CI Server이다. 

Ex) jenkins, Travis CI

### SCM(Source Code Management)
소스코드 형상 관리 시스템이 필요하다. 최근에는 Git과 연동되는 CI들이 많다.

### BuildTool
컴파일이나 테스트를 실시해 동작 가능한 소프트웨어로 만드는 BuildTool이 필요하다.
Maven이 이곳에 속한다.

### TestTool
작성된 테스트코드를 자동으로 실행해주는 도구가 필요하다.
Junit이 이곳에 속한다.