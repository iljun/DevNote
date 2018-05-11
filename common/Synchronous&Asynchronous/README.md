# Synchronous & Asynchronous

## Synchronous
A와 B라는 코드가 있을때, A라는 코드의 실행이 끝나야 B라는 코드를 실행하는 방법이다.

요청과 결과가 동시에 일어난다는 의미이다.

## Asynchronous
A와 B라는 코드가 있을때, A라는 코드를 실행시키고 끝나지 않아도 B코드를 실행하는 방법이다.

요청과 결과가 동시에 일어나지 않는다는 의미이다.

### 동기와 비동기를 구분하는 이유
동기 방식의 장점은 설계가 간단하고 직관적이지만, 결과를 기다리는 동안 다른 아무 행동도 하지 않는다.

비동기 방식은 좀 더 복잡하지만 결과가 주어지는 시간이 길어져도 다른 작업을 진행할수 있다는 장점이 있습니다.

이 장점은 자원을 좀 더 효율적으로 사용할수 있다는 의미입니다.

## Blocking
작업이 중단되는 의미이다.

네트워크 통신에서 요청이 발생하고 완료될때까지 대기하는것을 Blocking이라고 한다.

## Non-Blocking
작업이 중단되는 의미가 아니다.

네트워크 통신에서 요청이 발생하고 완료될때까지 대기하지 않고, 다른 작업을 수행할수 있다.

경우에 따라서는 효율과 반응속도가 뛰어나다.

## 장단점
* 동기식
    * 설계가 쉽고 직관적이다.
    * 하나의 작업이 오래걸리면 다른 작업을 하지 못하고 대기 상태에 빠진다.
    
* 비동기
    * 결과가 주어지는 시간에 관계없이 서로 다른 작업을 진행할수 있다.
    * 동기방식보다 복잡하고 설계가 어렵다.