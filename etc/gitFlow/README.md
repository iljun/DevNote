# gitFlow
다섯가지의 브랜치를 사용하는 전략이다.

가장 중심적인 브랜치는 master branch와 develop branch이다.

```
    * master branch : 배포상태의 branch
    * develop branch : 다음 버전의 branch
    * feature branch : 기능 개발 branch
    * hotfix branch : 배포상태의 branch에서 발생한 버그를 수정하는 branch
    * release branch : 배포 직전의 branch
```

## master branch
현재 배포되어 있는 branch이다.
master branch는 release branch 또는 hotfix branch에서 병합한다.

## develop branch
다음 버전의 개발중인 브랜치이다. 시작점은 master이다.
개발자들이 기능을 개발하고 develop branch에 merge하며, 이후 master branch로 merge한다.

## feature branch
기능 개발을 위한 branch이다.
develop branch에서 시작하며 하나의 기능이 완료되었을때 develop branch에 merge하고, branch를 삭제한다.


## hotfix branch
배포되어 있는 master branch에 장애가 생겼을 경우 긴급하게 해결하기 위해서 생성하는 브랜치이다.
hotfix branch에서 장애를 해결하고난후 master와 develop branch에 merge한다. 이후 삭제한다.
master branch에 병합후 tag 명령어를 이용해 기록을 남긴다.
또한 release branch가 존재한다면 버그 수정부분을 release branch에 병합한다.

## release branch
새로운 버전의 배포를 기다리는 branch이다.
지금 까지 개발된 내용을 delveop branch에서 따낸다.
master branch와 병합후 tag명령어를 이용해 버전을 명시한다.

또한 release branch에서 수정된 내용이 develop에 적용되어야 하기 때문에 develop branch와 병합한다.