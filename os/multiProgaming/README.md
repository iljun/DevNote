# 다중 프로그래밍 시스템(multi Programming System)

프로세서가 쉬지 않고 항상 수행할 작업을 가지게 함으로써 프로세서 이용률을 높이는 기법

그러나 버퍼링이나 스풀링으로는 프로세서의 이용률을 높이는데 한계가 있다.
    
메모리에 여러 작업을 두고, 운영체제가 메모리에 있는 작업 중 하나를 선택하여 실행한다.

실행 중인 작업이 다른 작업의 결과를 기다려야 하는 경우 프로세서가 유휴상태가 되는 대신 

메모리에 있는 다른 작업을 선택하여 실행한다.

## 장점
1. 동시에 여러가지 작업을 진행하기 때문에 성능이 좋다.

## 단점
1. 복잡하다.
2. 여러 작업을 메모리에 올려야 하기 때문에 메모리 관리 기법이 필요하다.
3. 여러개의 작업중 하나를 선택하기 위한 방법을 결정해야한다.