# 제어 흐름 문법 

## if 
보통 if문과 사용방법이 같다 
```
   if( expression ) {
        block
   } else
        block
```
## when
switch 문법을 대체하는 문법이다.
->을 이용해 연산을 수행한다.
```
    when(x) {
    
        1 -> ~~~
        2 -> ~~~~
        eles ->
    }
```
function에서도 곧바로 사용할수 있다는 특징이 있다.
```
    fun hasPrefix(x: Any) = when(x) {
        is String -> x.startsWith("prefix")
        else -> false
    }
```

if else 문의 대체로도 사용이 가능하며 함수의 반환값을 이용한 활용도 가능하다.
```
    when {
        x.isOdd() -> print()
        x.isEven() -> print()
        else -> print()
    }
```
## for
C#과 같은 문법이다. 하지만 난 C#문법을 모르기 때문에

```
    for(item in collection)
        print(item)
```
java의 forEach와 비슷하게 사용가능하다.

순차적인 index증가에는 범위식을 적용해 사용한다.

```
    for( i in 1..3)
        print()
        
    for( i in 6 downTo 0 step 2)
        print()
```
6 downTo 0 step 2 -> 6부터 2씩 감소하며 0까지 for문을 반복한다.
## while
일반 while문과 같다.

물론 do while구문도 사용 가능하다.