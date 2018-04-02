# Build & Compile

## Compile
소스코드를 분석해 기계어로 번역하는 과정

Java에서는 .java파일을 JavaCompile가 .class파일로 생성하는것

소스코드를 실행파일이나, 라이브러리같은 Object로 변환하는 작업

Compile과정 : 어휘분석 -> 구문분석 -> 의미분석

## Build
기계어로 번역된 것과 실행에 필요한 다른것들을 모아 실행가능 파일로 변경하는것

쉽게 얘기해서 작성한 sourceCode와 필요한 라이브러리 등을 모아 소프트웨어로 만드는 작업이다.

Compile은 Build의 부분집합 이라고 할수있다.

## Run
IDE에서 Run의 기능은 Compile + Build후에 실행시키는 일련의 작업이다.

## Link
하나의 Library나 Application을 만들 때 여러개의 sourceCode File로 구성한다.

그렇다면 하나의 File에서 다른 File의 함수, 메소드를 호출을 가능하게 하는것이 Link의 역할이다.

Build를 통해 실행 가능한 소프트웨어로 변경하지만 내부에서 Object끼리 연결하는 역할이 Link이다.