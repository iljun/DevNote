# enum

enum 서로 관련있는 상수들의 집합이라고 생각합니다.

enum타입은 고정된 상수로 RunTime시가 아닌 compileTime에 모든 값을 알고있어야합니다.

CompileTime에 모든 값을 알고있기 때문에 다른 패키지나 클래스에서 enum에 접근해 값을 변경할수 없다.

컴파일시에 타입의 안정성이 보장된다.
enum class는 내부에서 new키워드로 인스턴스 생성이 불가능하고 newInstance(), clone()등도 사용이 불가능하다.

이 때문에 생성자를 private로 생성해야한다. 이 때문에 enum은 실질적으로 final과 같다.

client에서 enum은 인스턴스를 생성할수 없고, 상속을 받을수도 없다.

그러므로 인스턴스 생성을 제어하며, 싱글톤으로 사용된다.

