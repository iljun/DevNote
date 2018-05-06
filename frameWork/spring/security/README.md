# Spring Security

## Spring Security 3 요소
* 접근주체(Principal)
    - 보호된 대상에 접근하려는 사용자
* 인증(Authenticate)
    - 현재 사용자가 등록된 사용자인지 알아내는 과정
* 인가(Authorize)
    - 현재 사용자가 특정 리소드,URL에 접근 할 권한이 있는지 검증 

## Spring Security 3 요소의 매칭
* 접근주체 -> Authentication
* 인증 -> AuthenticationManager
* 인가 -> Security Interceptor(Filter?)

### Authentication
* 인증 요청 시 요청 정보를 담는 역할
* 현재 접근하는 주체의 정보를 담고있다.

##### 주요 Method
* String getName() -> 사용자 이름
* Object getPricipal() -> 인증 주체 정보 Ex) loginId
* Object getCredential() -> 증명 값 Ex) password
* boolean isAuthenticatd()-> 인증 여부(인가와 인증은 다르다)
* Collection<? extends GrantedAuthority> getAuthorities() -> 현재 사용자가 가진 권한

### SecurityContext
* Authentication을 보관하는 역할
* 현재 사용자에 대한 Authentication을 구할때 사용 

### SecurityContextHolder
* SecurityContext를 보관하는 용도

### UsernamePasswordAuthenticationToekn
* 인증 객체이다.
* Java Doc를 참조하면 constructor가 2개이다.
    * 하나는 인증 전 객체를 생성(parameter 2개)
    * 다른 하나는 인증이 끝난 객체이다.(parameter 3개)
* UsernamePasswordAuthenticationToken에 권한 정보가 들어가있어야 인증이 끝난 단계이다.
    
### AuthenticationProvider
* 실제 인증이 일어나는 곳이다.
* 인증 전 객체를 받아 인증한 후 인증 후 객체를 만들어 돌려준다. 인증 실패시 예외를 생성한다.
* 개발자의 입맛에 맞추어 Custom하자
    * Custom하는 이유는 다양한 인증 로직이 생길수도 있으며, formLogin과 socialLogin을 둘다 적용할때 서로 다른 인증 로직이 필요하기 때문에
* 구현후 AuthenticationManager에게 등록
* formLogin이라면 UserDeatilsService를 구현한 객체와 passwordEncoder를 주입 후 사용한다.

### AuthenticationManager
* 실제 인증을 처리하는 역할
* 인증에 성공하면 인증 정보를 담고있는 Authentication을 리턴 실패시 AuthenticationException
* 개발자가 등록한 AuthenticationProvider들 에게 유일하게 접근하는 객체이다.

### SecurityFilterChain
//추후 추가 

### 동적으로 URL접근 권한 관리하기
1. Spring Security는 FilterInvocationSecurityMetadataSource를 통해 URL/Method에 접근 권한을 확인한다.
2. FilterInvocationSecurityMetadataSource에서 얻어온 ROLE과 사용자의 ROLE을 이용해 AccessVote를 진행한다.
