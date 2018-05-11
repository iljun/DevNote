# 분산 처리 시스템(distributed processing system)
시스템마다 운영체제와 메모리를 가지고 독립적으로 운영되며 필요에 따라 통신하는 시스템

여러개의 프로세서에 연산을 분리하는 장점

## 구성방법
1. 강결합 : 프로세서가 메모리와 클록을 공유하며 공유된 메모리를 통해 통신
2. 약결합 : 둘 이상의 독립된 컴퓨터 시스템을 통신선으로 연결

강결합과 약결합의 차이점은 메모리 공유의 여부이다.