# Reference Object

### Garbage 판단 기준
GC는 해당 객체가 Garbage인지 아닌지 판단하기 위해 Reachability라는 개념을 적용한다.

해당 객체에 유효한 Reference가 없다면 Unreachable로 구별하고 GC한다.

하지만 한 객체가 여러 객체를 다른 객체를 참조하고 그 객체들을 또 다른 객체를 참조할수 있다.

이 경우 유효한 참조가 있는지 판단하려면 항상 유요한 가장 상위의 처음 참조가 존재해야하는데 이를 Root Set이라고 한다.

Unreachable 객체가 Reachable 객체를 참조하더라도 자신이 참조 받지 못하면 Unreachable로 판단된다.

참조의 강도는 Strong reference > Soft reference > Weak reference > phantom reference 이다.

### Strong Reference
흔히 자바 객체를 new로 생성하는 경우를 Strong Reference라고 한다.

Root Set과 바로 연결되는 경우 

중간에 reference Object가 중가에 끼지 않은 상태이다.

### Soft Reference
Strong Reference가 아닌 것중에서 

Weak, Phantom Reference없이 Soft Reference만 통과하는 참조가 하나라도 존재하는 경우 

힙에 남아있는 메모리의 크기와 해당 객체의 사용빈도에 따라 CG여부가 결정된다.

자주 사용될때마다 더욱 오래 살아남는다.

### Weak Reference
WeakReference를 캠슐화한다.

WeakReference로 객체를 감싸게 되면 내부 객체에 null을 할당해도 

WeakReference참조가 살아있게 된다.

GC가 동작할때 unreachable 객체뿐만 아니라 weak reference객체도 가비지 객체로 간주되어 메모리에 회수된다.

rootSet으로 시작된 참조 사슬에 포함되어있어도 GC가 동작할때 회수되므로, 참조는 가능하지만 반드시 항상 유휴상태할 필요없는

LRU캐시와 같은 임시 객체들을 저장하는 구조를 만들수있다.

Weak Reference는 GC가 발생하기 전까지는 생존하지만 GC가 일어나면 바로 삭제된다.

### Phantom Reference
Strong, Soft, Weak 객체에 모두 해당하지 않는 객체를 의미한다.

finalize가 되었지만 아직 메모리가 회수되지 않은 상태 

Phantom Reference는 객체의 참조를 null로 설정하지 않고 참조된 객체를 phantom reachable 객체로 만든 이후에 

reference Queue에 enqueue된다.

이를 통해 객체의 finalize에 필요한 작업을 처리할수있다.

phantom reference는 soft, weak와는 다르게 GC대상 여부를 결정 부분에 관여하는게 아니라 

finalize와 메모리 회수 사이에 관여한다.

객체가 phantom reference로만 참조된다면 객체는 바로 finalize된다.

phantom reference는 어떤 객체가 finalize된 이후에 메모리가 회수되는 시점에서 사용자 코드가 관여할수 있게 한다.

후처리 작업후에는 사용자 코드에서 명시적으로 clear()메소드를 실행하여 null로 설정해야 메모리 회수가 된다.

## Reference Queue
soft Reference나 weak Reference는 GC의 대상이 되면 내부의 참조는 null이 되며 객체 자체는 ReferenceQueue에 enqueue된다.

enqueue작업은 GC에서 자동으로 진행한다.

Reference Queue에 referenceObject가 enqueue되어있는지 확인하면 객체가 GC가 되었는지 확인할수 있고,

이에 관련된 리소스나 객체에 대한 후처리 작업을 진행할수있다.

어떤 객체가 더 이상 필요없을게 됐을때 관련된 후처리를 해야하는 Application에서 사용된다.

Reference object들의 reachability가 변한 후 garbage collector에 의해 수거될 때 finalize()가 호출된 후 

그 reference object는 연관된 reference queue에 쌓이게 된다. 

이런 식으로 객체가 소멸되어 가기 전에 queue를 한번 거쳐감으로써 객체 소멸에 필요한 로직을 추가할 수 있게 해준다.
