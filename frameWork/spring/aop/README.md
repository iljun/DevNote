# AOP (Aspect Oriented Programming)
IOC와는 다르게 의존성 주입이 아닌 로직주입을 의미한다.

코드에 공통적으로 나타나는 부분을 외부로 빼내관리하고 외부에 위치한 코드를 주입하는 기법이다.

## AOP 만드는 방법

### XML

### 어노테이션
@Aspect를 이용해 클래스에서 AOP를 사용한다는 의미.

###### @Before
대상 메서드를 실행전에 실행시킨다는 의미

###### @After 
결과에 상관없이 메소드가 호출된 다음에 실행

###### @AfterRetuning
메소드가 성공적으로 처리된 다음 호출

###### @AfterThrowing
메소드가 실패하여 예외발생 이후 수정

###### @Around
메소드를 감싸 호출 전후에 실행

반환값을 반환하거나 예외를 던질수도 있다.

###### @JoinPoint
어플리케이션 실행에 Aspect를 끼워넣을 지점을 지정한다.

###### @PointCut
joinPoint를 매칭