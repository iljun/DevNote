# function

함수 선언의 자바와는 달리 ```fun```을 사용한다.

```
    fun function(x: Int): Int{
        return x * 2
    }
```

## Infix notation
```Infix```키워드를 이용해 중위 표현식을 사용할수 있다.

```
    fun Int.multiply(x: Int): Int{
        return this * x
    }
```
위 함수는 Int에 함수를 추가한 문법이다.

이때 ```var multiply = 3.multiply(10)```으로 사용가능하다.

다른 방법은
```
    infix fun Int.multiply(x: Int): Int{
        return this * x
    }
```
infix 키워드를 사용해 재정의한후 

```var multiply = 3 multiply 10```
중위표현식으로 사용가능하다.

## Named Parameters
함수 파라미터는 함수를 호출 할 때 이름을 지정해 줄수 있다.

함수를 선언할때 파라미터에 디폴트값을 지정해줄수있고, 디폴트 값을 지정해 주지 않아도 된다.

```
    fun namedParametersFun(x: Int = 100, y: Int = 200, z: Int)
```

```namedParametersFun(x = 200, z = 100)```
위와 같은 방식으로 호출이 가능하다. 

디폴트값이 없는 파라미터는 당연히 값을 넣어주는 것이 필수이다.

java에서는 파라미터의 순서로 구별했지만 namedParameter를 사용하면 순서에 관계없이 사용이 가능하다.

## Variable number of arguments
코틀린도 가변인자를 지원한다.

java에서는 ```...```를 이용해 가변인자를 사용했지만

kotline은 ```vararg```를 이용한다.

