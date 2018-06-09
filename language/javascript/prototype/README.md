# javaScript prototype
Javascript에서는 Class의 개념이 없다.(최근 ES6에는 Class개념이 생겼다고 한다.)

Class의 개념이 없으니 상속이 불가능하며 객체지향적 개발이 불가능하다.

하지만 JavaScript는 prototype이란 개념으로 객체지향적 개발을 가능하게 한다.

prototype을 이용해서 객체간의 상속관계를 맺을수 있다.

javascript에서 함수는 객체이다. 그러므로 생성자로서 사용될 함수도 객체이다.

객체는 프로퍼티를 가질수있다.

prototype은 그 용도가 특수한 프로퍼티이다.

prototype에 지정된 속성들은 생성자를 통해 객체가 생성될때 그 객체에 연결된다.

하지만 prototype이 상속의 목적이 아니다.

상위 객체들의 멤버들을 공유하여 사용하는 개념이다.

## prototype 과 prop
prop는 자기 자신을 의미한다.

상속의 효과를 보려면 prototype에 상속하려는 객체의 prototype을 대입시킨다.

그러면 prototype을 이용해 상위 객체에 prop에 접근할수 있어서 

상속의 효과를 볼수있다.

## prototype chain
객체의 생성 과정에서 모태가 되는 프로토타입과 연결되어 상속관계를 나타나게 할수 있다.

이때 이어지는 관계를 prototype chain이라고 한다.