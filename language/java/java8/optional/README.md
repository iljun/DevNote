# Optional
이전의 Java에서는 NullPointerException을 해결하기 위해
if문을 이용해 Null Check를 해주었다.

if문이 늘어날수록 가독성이 떨어지고 유지보수가 힘들어진다.

이러한 문제점을 해결하기 위해서 나온것이 Optional클래스다.

Optional클래스는 선택형값을 캡슐화하는 클래스다.

쉽게 얘기해서 Null 값이던 다른 값이던 Optional 클래스가 감싼다는 의미이다.
Optional클래스가 감싸고 있기 때문에 NullPointerException 예외가 발생하지 않고,
Null일 경우 다른방법으로 처리가능하며 디버깅이 쉬워진다.

만약 Null이 아니어야 하는 경우에 Null이 들어가있어 NullPointerException 예외가 발생한다면,
개발자는 Null이 어디서 생겨난것이고, 의도한 Null인지 버그에 관한 Null인지 디버깅을 통해 알아봐야한다.
Null 값이 할당되었을때 올바른 값인지 아니면 잘못된 값인지 판단할수 정보가 전혀 존재하지 않는다.

또한 Optional 클래스를 사용한다면 Model의 의미가 더욱 분명해진다.
만약 Optional 클래스로 감싸져있는 Model은 해당 클래스의 값이 있을수도있고 없을수도 있다는 의미로 Model의 의미가 더욱 분명해진다.