# raceCondition

## 경쟁상태(race condition)
둘 이상의 입력이나 조작 때문에 두개의 프로세스가 하나의 자원을 가지고 경쟁하는 상태

두개의 프로세스가 동시에 하나의 자원에 접근하기 때문에 의도치 않은 결과를 얻을수 있다.

## 라이브락(Livelock)
하나의 프로세스가 하나의 자원을 점유하고 있을때 다른 프로세스가 해당 자원을 사용하기 위해 무한정으로 대기상태에 빠지는것

## 교착상태(DeadLock)
두개 이상의 프로세스가 서로 상대방의 자원을 요청해 서로 대기상태에 빠져 아무 작업도 하지 못하는 상태

### DeadLock의 4가지 조건
 * 자원점유와 대기
    * 자원을 가지고 있는 상태에서 다른 프로세스가 할당받은 자원의 반납을 대기하는것.
    
 * 비선점
    * 다른 프로세스가 할당받고 있는 자원은 사용이 끝날때까지 강제로 빼앗지 못한다.
 
 * 순환대기
    * 각 프로세스가 순환적으로 다음 프로세스가 요구하는 자원을 자기고있는것
 
 * 상호 배제
    * 하나의 자원은 하나의 프로세스만 사용 가능하다.