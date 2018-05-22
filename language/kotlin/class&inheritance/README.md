# Class & Inheritance

## Class
kotlin의 class도 class키워드를 이용한다.

```
    class Invoice{
    
    }
```

### constructor
kotlin또한 default생성자 이외로 추가로 생성자를 지정할수 있다.

```
    class Person constructor(firstName: String){
    
    }
    
    또는 
    
    class Person(firstName: String){
    
    }
    으로도 constructor 키워드를 생략 가능하다.
```


```
    default생성자가 아닌 다른 생성자는 
    class Person{
        constructor(parent: Person){
            parent.children.add(this)
        }
    }
    이러한 방식으로 사용 가능하다.
    
    만약 동일한 클래스의 다른 생성자를 사용하는 방법은
    
    class Person(val name: String){
        constructor(name: String, parent: Person) : this(name){
            parent.children.add(this)
        }
    }
```
#### var vs val
kotlin의 변수를 키워드이다.

차이점은 var는 수정 가능하며 val은 수정 불가능하다.

### 접근제어자
private - 클래스 내부에서만 접근 가능

protected - 클래스 내부와 자식 클래스에서 사용 가능 

internal - 같은 모듈 내부에서 모두 사용 가능하다.

public - 어디서나 사용 가능하다.

### init
정확한 개념은 아직 파악하지 못했다.

하지만 생성자보다 먼저 실행되는 block이다.

```
    class Constructors{
        init{
            println("init block")
        }
        
        constructor(i: int){
            println("Constructor")
        }
    }
    
    출력결과는 
    init block
    Constructor
```

### open
kotlin의 모든 클래스는 기본적으로 final형태이다.

상속을 받을수 없는 class이기 때문에 

```
    open class Base(){
    
    }
    
```
이러한 코드로 상속 가능한 class로 변경한다.

## Inheritance
상속의 키워드는 
```
    class MyView : View {
    
    }
```

MyView class에서 view class를 상속받는다.

생성자 내부에서 super()를 사용해 상위 클래스의 생성자를 호출한다.

## method Override
kotlin의 모든 class는 final이라고 했고 method또한 마찬가지이다.

method에서도 open을 사용해 상속 가능한 상태도 변경시킬수있다.

또한 java에서 @Override 어노테이션처럼 

override 키워드를 사용한다.

java는 어노테이션이 선택이었지만 kotlin은 필수이다.

```
    open class Base{
        open fun v(){}
        fun nv(){}
    }
    
    class Derived(): Base() {
        override fun v() {}
    }
```

또한 하위클래스에서 method override이후 다른 클래스에서 재정의 하지 못하도록 final키워드를 붙여줄수도 있다.

## properties overriding
method이외로 속성도 재정의가 가능하다.
```
    open class Foo {
        open val x: Int get() {...}
    }
    
    class Bar1 : Foo() {
        override val x: Int = ....
    }
```

var 속성으로 val을 재정의 할수도 있지만 반대는 가능하지 않다.

val는 기본적으로 getter 메서드를 선언하고 var로 다시 재정의한다면 setter를 추가로 선언하기 때문에
readOnly라는 속성이 깨지기 때문에 불가능하다.

## super
상위 클래스의 function을 호출할때 super키워드를 사용한다.

이 super클래스를 inner 클래스에도 사용가능하며 label기능을 사용할수 있다.

```
    class Bar : Foo(){
        override fun f() {}
        override val x: Int get() = 0
        
        inner class Baz{
            fun g(){
                super@Bar.f()
                println(super@Bar.x)
            }
        }
    }
```

### 상속 규칙
인터페이스와 class를 동시에 구현하고 상속할수 있다.

이때 같은 이름의 메소드를 재정의 할수있고, 상위 메소드를 호출할 경우도 있다.

이런경우 class와 interface를 선택해야하기 때문에 한가지 기능이 주어진다.

```
    open class A {
        open fun f() { }
        fun a() {}
    }
    
    interface B {
        fun f() {  }
        fun b() {  }
    }
    
    class C() : A(), B {
        override fun f(){
            super<A>.f()//a class의 f fun 출력 
            super<B>.f()//b interface의 f fun 출력
        }
    }
```

## Abstract class
Abstract 키워드를 이용한다.
```
    open class Base {
        open fun f() {}
    }
    
    abstract class Derived : Base(){
        override abstract fun f()
    }
```

## data Class
흔히 java에서 데이터 저장용 class를 생성하는 경우가 있다.

이때 java에서는 getter/setter, hashcode/equals, toString등 Lombok을 이용하거나 직접 정의해야 하는 경우가있다.

이 기능을 kotlin에서는 자동으로 지원해준다.

바로 class 앞에 data를 붙여주게 된다면 

data class가 필요한 기능들은 모두 자동으로 만들어준다.

- constructor
- getter/setter
- hashcode/equals
- toString
- componentN() funcionts
- copy() function

#### componentN
처음보는 신기한 기능이다.

쉽게 N번째 값을 자유롭게 꺼낼수있는 방법이다.

```
    val id = user.component1()
    val name = user.component2()
```
위와 같은 방식으로 편리하게 값을 꺼낼수있다.

하지만 유지보수 관점에서는 좋은 기법인지는 정확히 모르겠다.

#### copy
java의 clone과 비슷한 개념이다.

말그대로 복사를 하는 개념인데 clone과는 조금 다르게

일부 프로퍼티를 변경할수 있고 나머지는 그대로 유지할수 있다.

```
    val user = User(1,"wonwoo") 
    -> name이 wonwoo로 변경되고 나머지 필드는 그대로 유지된다.
```


## Object
코틀린에서는 static한 함수가 존재하지 않는다.

그것을 대체할수 있는 object라는 것을 지원해준다.

```
    object Utils{
        fun sum(a: Int, b : Int) = a+b
    }

    Utils.sum(1,10)
```
이러한 방식으로 사용한다.

