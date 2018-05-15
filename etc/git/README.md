# Git
소스코드를 분산 관리하기 위한 형상 관리 도구이다.

## SVN vs Git
가장 큰 차이점은 SVN은 중앙 집중식 소스코드 관리이며 , Git은 분산 소스코드 관리이다.
Git은 중앙 저장소의 문제가 생겨도 분산되어 있는 로컬 저장소를 이용하여 중앙저장소를 복구 가능하다.

## Git의 흐름
1. Local repository에서 작업한 내용을 commit후 Remote repository로 push
2. remote repository에 변경된 사항을 협업을 하는 단위끼리 Pull로 내려받는다.

## Git fork
* Upstream Remote Repository : 개발자들이 공유하는 저장소, 최신 소스코드가 저장되어 있는 원격 저장소
* Origin Remote Repository : Upstream Repository를 Fork한 원격 개인 저장소
* Local Repository : 개인 저장소

개인 repository로 fork를 한다면 그 저장소는 Origin Remote repository가 된다.

이때 Local repository에서 작업을 완료한 후 

origin remote repository로 push를 한다 

이후 upstream remote repository에 pull request를 이용해 반영한다.

## Git의 장점
1. 병렬 개발이 가능해지며, 버전관리가 용이하다.
2. 수정 내역이 commit단위로 가능하다. 또한 commit기록이 남아있기 때문에 이전의 소스코드로 언제든지 돌아갈수있다.
3. 인터넷이 연결되어있지 않은 곳에서도 개발이 가능하며, 중앙 저장소의 문제가 생겨도 복구 가능하다.

## Git의 중요 시나리오
작업한 내용을 스테이지에 올려(add) 로컬에서 commit후 push를 통해 원격저장소에 반영한다.

## Git 명령어
```
    * clone : 원격 저장소에서 로컬저장소로 소스코드를 복사해온다.
    * add : 로컬 stage에 변경사항을 올린다.
    * commit : stage에 올라와있는 변경사항을 저장한다.
    * push : commit 된 변경사항을 원격 저장소에 올린다.
    * pull : 원격 저장소의 내용중 로컬 저장소의 반영되지 않은 부분까지 저장한다.
    * tag : commit의 위치를 쉽게 찾아갈수있게 달아 놓은 이름표의 개념이다.
    * checkout : 특정 시점의 브랜치나 소스코드로 이동하는 명령어이다.
    * merge : 하나의 브랜치를 다른 브랜치와 병합하는 명령어
    * branch : 독립적인 작업을 진행하기 위해 하나의 브랜치에서 독립된 작업공간 
    * revert : 이전의 commit 내역으로 돌아가는 명령어 현재까지 작업한 내용들은 유지된다.
    * reset : 이전의 commit 내역으로 돌아가며 현재까지 작업한 내용들이 사라진다.
```

### fork vs clone
fork는 github의 기능이다. clone의 외부저장소의 소스코드를 자신의 local로 복사하는것을 의미하며,
fork는 외부저장소의 내용을 자신의 github에 복사하여 repository를 만드는 행위이다.