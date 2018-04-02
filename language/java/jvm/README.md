# Java Virtual Machine

JVM의 메모리 구조는 크게 class, stack, heap, PC 레지스터, native 메소드 영역으로 구분됩니다.

class 영역은 클래스, 변수, 메소드, 상수, static 변수에 대한 정보가 저장됩니다.

stack 영역은 메소드가 실행될때 메소드의 지역변수, 파라미터등의 정보가 저장되고 메소드 호출이 끝나게되면 공간을 삭제하게 됩니다.

heap 영역은 java의 객체가 생성될때 저장되는 공간입니다. new 키워드를 사용해 객체나 배열을 생성했을대
이 heap영역에 저장되게 됩니다.

heap 영역은 new 영역, old 영역, perminant 영역으로 구분됩니다.

new 영역은 객체가 처음 생성될때 저장되는 영역입니다.
new 영역은 하나의 eden 영역과 두개의 survivor 영역으로 구분됩니다. 
객체가 처음 생성될떄 eden 영역에 생성되게 됩니다. 만약 eden영역이 가득차게 되었을때 참조하는 변수가 있는 객체만
survivor의 영역으로 옮기고 참조가 남아있지 않은 객체들은 삭제하게 됩니다. 

이 과정을 minor Garbage Collection라고 합니다.

이러한 과정이 계속 반복되면서 일정시간동안 계속 참조되는 객체들은 old영역으로 옮기게 됩니다.

old 영역이 가득하게 됐을때 application이 잠시동안 멈추면서 old영역에 있는 참조가 없는 객체들을 모두 삭제하게됩니다.
application이 잠시동안 멈추고 시간이 오래걸리는 단점이 있습니다. 

이 과정을 major garbage collection이라고 합니다.

Permanant영역은 JVM클래스의 Mehtod와 객체를 저장

PC 레지스터 영역은 쓰레드가 생성될떄 마다 쓰레드가 어떠한 명령을 실행할지 저장합니다.

native 메소드 영역은 java이외의 언어에서 제공되는 메소드가 저장되는 공간입니다.

## JVM의 실행순서
1. java 파일을 컴파일러가 .class파일로 생성
2. .class 파일을 classLoaderSystem이 읽어들인다.
3. Excution Engine에 의해 .class파일을 기계어로 변환해 Runtime Data Area에 적재