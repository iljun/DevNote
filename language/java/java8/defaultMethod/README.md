# defaultMethod
호환성을 유지하면서 API를 변경 가능하게하는것이 default Method이다.

만약 인터페이스가 변경된다면, 인터페이스를 구현하는 모든 클래스들이 해당 메소드를 구현해야하는 문제점이있다.

이러한 문제점을 해결하기 위해서 인터페이스의 메소드를 구현해 놓을수 있게 만들었다.

인터페이스가 이미 구현해놨으니 해당 인터페이스를 구현하는 클래스에서는 해당 default Method를 상속받게 된다.

가장 큰 예시는 List interfacee의 Sort method와 Collection interface의 stream Method이다.

## 다중상속의 문제점을 어떻게 해결하는가???
Java8에서는 동일한 Method명을 가지는 default Method를 상속받을때 3가지 규칙을 따라야한다.

1. 클래스나 슈퍼클래스에서 정의한 Method가 default Method보다 우선권을 가진다.
2. 클래스나 슈퍼클래스에 Method의 정의가 없을경우 default Method를 구현한 인터페이스가 선택된다.
3. 만약 인터페이스간의 우선순위가 없을때, Method를 재정의 해야한다.