# String class

문자열을 처리하기 위한 기본적인 클래스입니다.
String class는 immutable한 class입니다.
한번 생성되면 변환되지 않는다는 의미입니다.

그러면 문자열을 변경하기 위한 클래스는 StringBuilder class 와 StringBuffer class가 존재합니다.

StringBuilder와 StringBuffer는 사용법은 같지만 Thread에 동기화 여부가 차이점입니다.

StringBuilder class는 Thread에 동기화가 되어있지 않고,
StringBuffer class는 Thread에 동기화가 되어있습니다.

jdk 1.5버전 이후에는 String class의 +연산시 내부적으로 StringBuilder class를 이용한 구현으로 변경되어있습니다.

## String class의 사용이유
문자열을 변경하는데 적절하지 않은 String class를 사용하는 이유는
변경이 적고 참조가 많은경우 여러개의 쓰레드에서 문자열을 공유하는 경우 별다른 동기화를 구현하지 않아도 사용가능하기 때문입니다.

## 상수 풀(constrant poll)
상수풀이란 JVM heap영역의 permanent generation 영역에 생성되어 자바 프로세스가 종료될때까지 객체를 유지시키는 곳이다.
String 객체는 상수 풀에서 관리되는데 그 이유는 중복 문자열에 대한 메모리관리 때문이다. 같은 문자열이 존재할때 동일한 문자열이
상수 풀에 삽입되는것은 메모리 낭비이기 때문이다. 이미 존재하는 문자열을 삽입시 heap에 생성된 객체의 문자열을 해제하고 상수 풀에 존재하는 문자열의 reference주소를 넘겨준다.

그렇다면 String class를 상수 풀에 등록하는 방법은 2가지이다.

1. ""을 사용하여 객체를 생성하는것.
    "" 을 사용하여 객체를 생성하면 자동으로 상수풀에 등록된다.

2. 생성자를 이용한 경우는 상수풀에 자동등록이 되지 않고 heap영역에 객체가 생성된다.
   이 객체를 상수풀에 등록하려면 String Class의 intern() Method를 호출하면 된다.
   
상사 풀에 등록된 문자열은 == 연산자를 이용해 두 문자열이 같은 문자열인지 판단할수 있습니다.
하지만 heap에 등록된 문자열은 == 연산자를 이용해 같은 문자열인지 판단할수 없습니다.