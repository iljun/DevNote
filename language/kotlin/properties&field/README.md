# Properties & fields

## 변수선언
var나 val 키워드를 사용해 변수를 정의한다.

``` 
    var <propertyName>[ : <PropertyType> ] [= <property_initializer>]
    var name: Type = ...
    val name: Type = ...
```

kotlin은 getter와setter를 자동지원하며 개발자가 직접 정의해 사용할수도 있다.

그렇다면 var와 val의 차이점은?

var는 우리가 사용하는 일반적인 변수선언의 키워드이다.

val는 readOnly속성을 가지며 setter는 지원되지 않는다.

그렇다면 속성에 대한 재정의시 var와 val는 서로가 가능할까?

var를 val로 재정의는 가능하지만 val를 var로는 재정의가 불가능하다.

val는 readOnly속성이며 setter를 가질수 없다.

val변수를 var로 재정의하게 된다면 setter가 자동으로 생기기 때문에 readOnly의 성질이 깨지게된다.


## getter setter
```
    var <propertyName>[: <PropertyType>] [= <property_initializer>]
        [<getter>]
        [<setter>]
        
    ex)
        val isEmpty: Boolean
            get() = ...
            
        var string: String
            get() = this.toString()
            set(value) {
                setDataFromString(value)
            }

```
만약 getter와 setter를 제공하고 싶지 않다면
```
    var setterVisibility: String = "abc"
        private set
```

만약 getter를 통해 필드의 타입을 추론할수 있다면 프로퍼티의 타입을 생략 가능하다.

## Backing Fields
코틀린에서는 간단하게 getter와 setter에서 validation을 구현할수있다.

이때 getter와 setter에서 사용할수 있는 변수를 Backing Field라고 한다.

이 필드를 이용해 validation후에 값을 초기화하거나 return할수있다.

## Compile-Time Constants
const modifier를 이용하면 컴파일 타임 상수를 만들수 있다.

