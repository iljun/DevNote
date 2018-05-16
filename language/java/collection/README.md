# Collection Class
같은 데이터 타입을 쉽게 저장하기 위한 class입니다.

## Collection class의 대표 인터페이스

* List : 순차적인 데이터를 저장하며 중복을 허용합니다.
    * ArrayList : 가변적인 길이를 가질수있는 클래스입니다.
    * LinkedList : doubly Linked List로 구현된 클래스입니다.
    * Stack : stack자료구조를 구현한 클래스입니다.
    * Vactor : ArrayList와 동일한 기능을 가진 클래스, 쓰레드에 동기화가 구현되어있다.
     
* Set : 데이터의 순서가 존재하지 않고, 중복을 허용하지 않습니다.
    * HashSet : 내부적으로 해싱을 이용해 구현
    * TreeSet : 이진탐색트리의 형태로 데이터를 저장
        * TreeMap을 기반으로 내부 구현이 되어있다. 마찬가지로 key값에 의해 정렬된다.
    
* Map : Key - value형태로 데이터를 저장하며, 데이터의 순서가 존재하지 않고, 중복을 허용하지 않습니다.
    * HashMap : key - value형태로 저장되는 hashMap의 자료구조
    * HashTable : HashMap과 기능은 동일하지만 동기화가 구현되어있다.
    * TreeMap : key - value형태로 자료를 저장하지만 트리의 형태로 저장되는 자료구조
        * Red-Black 트리를 기반으로 구현되어있다. Map은 key값에 의해 정렬된다. 이때 정렬기준은 제공해놓은 Comparable에 의해 정렬된다.

### TreeSet , TreeMap
두 자료구조 모두 트리를 기반으로 구현되어있기 때문에, 정렬이 가능하다.

Collection class중에서 Tree가 붙은 구현체들은 모두 자동으로 정렬이된다.(기본 class를 사용할시)
Set이 붙은 구현체들은 모두 중복을 허용하지 않는다.쉽게 중복을 제거한다는 의미이다.        