# Template Method Pattern

상속을 통해 기능을 확장하는 패턴이다.

상위 클래스에서 뼈대를 정의하고, 하위 클래스에서 구체적인 내용을 정의한다.

여러 클래스에서 공통적으로 사용되는 사항은 상위 추상클래스에 구현하고,

상세 부분은 하위 클래스에서 구현하는 방식이다.

어떤 알고리즘의 틀이 결정된 상태에서 구체적인 구현은 서브클래스에게 맡기는 패턴.

코드의 중복을 줄이고, refactroing에 유리한 패턴으로 상속을 통한 확장 개발방법이다.

상위 클래스만 보고 어떠한 방식으로 작동하는지 파악할수 있고,

실제 구현은 하위 클래스에서 구현한다.   