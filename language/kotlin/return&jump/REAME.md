# return & jump

## label
```
    loop@ for(i in 1..100){
        for(j in 1..100){
            if(...)
                break@loop
        }
    }
```
label이라는 기능을 이용해 break와 continue등을 모두 구현할수 있다.

label이 붙은 block을 탈출하거나 그 block으로 돌아가는 기능이다.
## return
label기능을 사용해 return 또한 구현 가능하다.

```
    fun foo(){
        listOf(1,2,3,4,5).forEach lit@{
            if(it==3)
                return @lit
            print(it)
        }
       print(" done with explicit label")
    }
```
