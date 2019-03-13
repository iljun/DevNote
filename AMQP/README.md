# AMQP(Advanced Message Queuing Protocol)
오픈 소스에 기반한 표준 프로토콜이다.

이미 상용화된 MQ 제품들은 많았지만, 대부분 플랫폼 종속적이기 때문에 서로 다른 이기종끼리의 메세지 교환이 어려웠다.

메세지 브릿지를 사용하거나, 시스템자체를 통일시켜야하는 불편함이 존재했다.

AMQP는 그 단점을 보완한 프로토콜이다.

서로다른 이기종간의 종속성 없이 최대한 효율적으로 메세지를 교환하기 위한 프로토콜이다.

서로 다른 이기종간의 메세지 교환을 하기 위해 AMQP는 몇가지 제안사항이 있다.

1. 모든 broker들은 같은 방식으로 작동한다.
2. 모든 client들은 같은 방식으로 작동한다.
3. 네트워크를 통해 전송되는 명령어들을 모두 표준화
4. 프로그래밍 언어에 중립적이다.

# AMQP Routing Model
AMQP의 Routing Model에는 중요한 3가지 Component가 존재한다.
1. Exchange
    
    publisher(메세지를 전송한 주체)에서 받은 메세지를 다른 Queue 또는 다른 Exchange에 routing하는 기능
    
    라우팅하는 방법은 Queue나 Exchange는 Exchange에 Binding되어 있고 이 Binding에 따라 알맞은 Queue, Exchnage에 routing이 된다.
    
    Binding이 되는 기준은 Routing key이다.
    
    Routing key를 기준으로 Queue나 Exchange에 Binding된다.
    
    Binding과 메세지를 일치시키기 위한 알고리즘이 Exchange Type이다.
    
    Binding과 ExchangeType은 다른 개념이다.
    
    Binding은 어느 Queue 또는 Exchange에 보낼지에 대한 정보이며,
    
    ExchngeType은 어떤 방법으로 라우팅 시킬지에 대한 알고리즘이다.
    
2. Queue
    
    일반적으로 알고있는 Queue이다.
    
    전달 받은 Message를 디스크 또는 메모리에 적재 후 consumer에게 전달한다.
    
    큐는 Exchange로 Binding되어 메세지를 전달 받는다.
    
3. Binding
    Exchange와 Queue의 관계를 정의한 개념이다.
    
    하나의 Queue에 여러 exchange가 Binding 될 수 있으며, 하나의 exchange에 여러개의 queue가 binding될 수 있다.
    
    하나의 Queue에 여러 exchange가 Binding 될 때
    
    하나의 Queue에서는 여럭 exchange를 통해 여러 Message를 적재하게 되며,
    
    하나의 exchange에 여러개의 Queue가 Binding 되었을때,
    
    여러개의 Queue는 하나의 exchange를 통해 들어온 Message들이 각각 적재된다.
    
# Exchange Type
어떤 방법으로 Message를 라우팅할지 결정하는 알고리즘이다.

AMQP에서는 표준 Exchange Type으로 Routing key에 기반한 아래 3개의 라우팅 알고리즘과 key-value 헤더에 기반한 1개 유형의 Exchange Type들을 반드시 정의하도록 되어있다.

1. Direct Exchange

    메세지를 큐에 1 : N으로 매칭시키는 방법이다.
    
    동일한 Routing Key를 가진 큐에 모든 Message를 전달하는 알고리즘이다.
    
2. Topic Exchange
    
    와일드 카드를 이용해 매칭시키는 방법이다.
    
    라우팅 키는 "."으로 구분된 단어의 집합이며, 와일드 카드 문자를 이용해 각 큐에 Binding된다.
    
    "*"는 하나의 단어, "#"은 0개 이상의 단어를 의미한다.
    
    routing key가 "iljun.test"라면 "*.test.#" "iljun.*"로 라우팅 될 수 있다.
    
3. Fanout Exchange
    
    모든 메세지를 모든 큐에 라우팅하는 방법이다.
    
4. Headers Exchange

    key-value로 정의된 Header에 의해서 라우팅하는 기법이다.
    
    큐를 바인딩할때 x-match라는 특별한 arguments를 이용해 Binding 조건을 명시한다. (all, any)
    
    all이라면 and의 개념이고, any이면 OR의 개념이다.