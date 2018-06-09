# Spring Boot jsp 404 issue

Spring Boot는 기본적으로 jsp를 지원하지 않는다.

thymeleaf를 지원한다.

하지만 dependency를 추가하면 jsp를 실행할수있다.

여기서 설명하려는 issue는 SpringBoot는 jar파일로 변환해 간단하게 실행가능한데 이때 jsp가 404에러로 찾을수 없다.

이유는 SpringBoot가 jar파일로 빌드할때 jsp가 속해있는 webapp폴더를 무시하고 빌드하기 때문에

local에서는 webapp폴더를 찾기 때문에 404를 경험하지 못하다가,

실제 서버에 배포했을때 404에러를 만나는 이유이다.

이 이슈를 해결하기 위한 방법은 3가지이다.

1. jar파일 형태가 아닌 war파일을 이용하는 방법

2. 1.4.3 이전 버전들은 webapp폴더를 ```resource/META-INF``` 밑에 위치시키면 간단히 해결 가능하다.

3. 1.4.3 이후 버전들은 ```resource/META-INF```의 하위의 뷰를 허용하지 않는 것으로 변경되었다.
    - JAR을 포기하고 webapp 폴더를 쓰는 WAR를 선택해야한다.
    - 또는 maven 설정으로 webapp 폴더를 포함해야한다.
```
    <build>
        <resources>
			<resource>
				<directory>src/main/webapp</directory>
			</resource>
		</resources>
	</build>
```