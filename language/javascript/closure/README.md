# closure
javaScript 클로저의 개념은 

outer함수 내부에 지역변수를 inner함수가 참조할 경우 

outer함수가 return되어 GC되었을때 

inner함수가 변수를 참조하고 있기 때문에 GC가 되지 않는 개념이다.

GC가 되지 않기 때문에 메모리릭이 발생할수 있기 때문에 최소화 해야한다.

js에서는 closure개념을 이용해 private를 구현할수 있다.