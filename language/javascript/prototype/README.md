# javaScript prototype
Javascript에서는 Class의 개념이 없다.(최근 ES6에는 Class개념이 생겼다고 한다.)

Class의 개념이 없으니 상속이 불가능하며 객체지향적 개발이 불가능하다.

하지만 JavaScript는 prototype이란 개념으로 객체지향적 개발을 가능하게 한다.

prototype을 이용해서 객체간의 상속관계를 맺을수 있다.

## prototype 과 prop
prop는 자기 자신을 의미한다.

상속의 효과를 보려면 prototype에 상속하려는 객체의 prototype을 대입시킨다.

그러면 prototype을 이용해 상위 객체에 prop에 접근할수 있어서 

상속의 효과를 볼수있다.