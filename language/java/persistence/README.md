# Java Persistence API
자바 플랫폼 SE와 자바 플랫폼 EE를 사용하는 응용프로그램에서 관계형 데이터베이스의 관리를 표현한느 자바 API.

## persistence(영속성)
데이터를 생성한 프로그램의 실행이 종료되더라도 사라지지 않는 데이터의 특성이 영속성이다.

## Java Persistence API Annotation
### @Entity
해당 클래스가 엔티티임을 알리기위해 사용.

어플리케이션이 실행 될때 엔티티 자동검색으로 클래스들을 엔티티빈으로 등록한다.

### @Table
데이터의 저장소, 테이블을 의미한다.

생략했을시 클래스의 이름을 자동으로 테이블의 이름으로 인식한다.

### @Id
엔티티빈의 기본키를 의미한다.

하나의 엔티티에 반드시 존재해야한다.

### @GeneratedValue
데이터베이스에 의해 자동으로 생성되는 값

### @Enumerated
열거형 타입을 지정한다.

ordinal이라고 부르는 인덱스 값과 연동되는데 index값이 아닌 String값을 사용하는걸 추천한다.

index값을 사용하게 된다면 테이블 구조가 변화했을때 기존 데이터를 모두 변화해야하는 단점이 생길수도있다.
### @Column
필드와 테이블의 컬럼을 매핑시키는 역할

생략가능하며 생략시 필드의 이름이 테이블의 컬럼으로 자동으로 매핑
#### name(String)
필드와 매핑될 컬럼의 이름

#### nullable(boolean)
해당 컬럼이 null을 허용하는지에 대한 여부

#### lenght(int)
컬럼의 길이값

#### unique(boolean)
컬럼이 유일한 값을 가져야하는지에 대한 여부

#### insertable(boolean)
엔티티가 영속될때 insert에 참여할지 말지를 결정

#### updatable(boolean)
변경된 필드의 값을 테이블에도 반영할지를 결정


## @ManyToOne
참조 Entity가 One이고 대상 Entity가 Many인 경우

## @OneToMany
참조 Entity가 Many이며 대상 Entity가 One인 경우 

## @OneToOne
참조 Entity와 대상 Entity가 1 대 1 로 매핑되는경우

## @ManyToMany
참조 Entity와 대상 Entity가 N 대 N 으로 매핑되는 경우