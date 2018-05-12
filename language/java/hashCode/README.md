# hashCode & equals
객체를 구별하기 위한 고유의 정수이다.
Object의 hashCode는 heap에 생성되는 객체의 주소를 바탕으로 생성한다.

Java 기본객체인 Integer,String 같은 클래스들은 모두 hashCode와 equals가 정의되어있다.

hashCode는 해시테이블같은 자료구조를 사용하기 위한 하나의 인덱스라고 할수있다.

그렇기 때문에 직접 생성한 객체에서는 hashCode를 재정의 해주어야한다.

hashTable을 사용할 때 같은 내용의 객체인데 hashCode값이 다르다면 다른 value라는 오류가 생길수도 있다.
 
hashCode가 필요한 이유는 객체가 같은 값을 가질 때 같은 해쉬코드를 반환해야지
hashTable을 사용할때 제대로된 key값의 역할을 할 수 있기 때문이다.

결과적으로 equals를 재정의할때는 hashCode또한 재정의 해야한다.

만약 모든 객체의 hashCode가 같다면 
Java의 hash관련한 Collection에서 성능이 최악으로 떨어질것이다.

hash에 관련된 Collection은 객체의 hashCode를 key값으로 사용하기 때문에 엄청난 Collision이 발생할것이다.

### hashCode Override
```
    @Override
    public int hashCode(){
        return Object.hash(..필드);
    }
```

### equals Override
```
    @Override
    public boolean equals(Object obj){
        if(obj==null)
            return false;
            
        if(obj.getClass!=해당클래스.class)
            return false;
        
        해당클래스 변수 = (해당클래스)obj;
        if(...)-->필드비교
    }
```