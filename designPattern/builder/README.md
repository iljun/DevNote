# Builder pattern

빌더패턴도 팩토리패턴과 유사하게 새로운 객체를 생성하는 패턴이지만, 동작 방식은 조금 다르다.

빌더패턴은 생성자에 매개변수를 차례차례 받아 build라는 메소드를 통해 객체를 생성한다.

빌더패턴은 텔레스코핑 생성자와 자바빈즈 패턴의 단점을 보완하고자 하는 디자인 패턴이다.

텔레스코핑 생성자의 단점은 매개변수의 수가 많아지면, 생성자의 갯수또한 많아지고, 사용자의 입장에서는 매개변수의 순서와 데이터타입, 갯수까지 모두 세어야한다.

또한 유지보수에도 매우 비 효율적이다.

자바빈즈 패턴의 단점은 setMethod를 통해 객체의 필드값을 채워넣기 때문에 일관성있는 객체를 생성하지 못할수 있다는 단점이 있습니다.

또한 유지보수시에도 비 효율적이다.

특정 객체를 바로 생성하는 대신에 , builder의 생성자의 필수 매개변수들을 Parameter로 입력받고 build 메소드를 통해 객체를 생성한다.

코드의 가독성도 증가하며 코드의 작성이 쉽다.

단점은 builder class가 추가적으로 필요하다. 

## 코드
```

```