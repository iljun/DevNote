# Thread
동작하고 있는 하나의 프로그램을 프로세스라고 칭하고, 그 프로세스안에서 힙영역을 공유하면서
동시에 여러가지 일을 하는것이 쓰레드이다.

자바에서 쓰레드를 구현하는 방법은 2가지이다.

## Thread Class extends
Thread class를 상속받아 구현하는 방법이니다.
이미 Thread class를 상속받았기 때문에 다른 클래스를 상속받을수 없습니다.
run Method를 구현하고 생성된 인스턴스의 start Method를 실행해야 thread가 실행됩니다.

## Runnable interface implements
Runnable interface를 implements해서 run메소드를 재정의 하는 방법입니다.
위와 같이 run메소드를 재정의하고 start Method를 실행해야 thread가 실행됩니다.