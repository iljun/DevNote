# Spring container Life Cycle
스프링 컨테이너의 생명주기는 4가지이다.

1. 생성

```ApplicationContext act = new ApplciationContext();```

2. 설정

```
act.load("bean"); 
act.refresh();
```

3. 사용

```Bean bean = act.getBean("beanName");```

4. 종료 

```act.close();```


# Spring Bean Life Cycle
1. POJO Bean을 인스턴스화 하지 않은 상태로 빈 설정 정보를 초기화한다.

2. Bean 인스턴스를 생성하면서 의존관계에 있는 Bean이 존재하는지 파악한다, 존재하지 않는다면 초기화 실패

3. Bean끼리의 의존관계가 체크된다면 각 injection에 맞게 값을 넣어주거나, reference를 전달

4-1. BeanNameAware를 구현 시 setBeanName()호출

4-2. BeanClassLoaderAware를 구현 시 setBeanClassLoader()를 호출

4-3. ApplicationContextAware를 구현 시 setApplicationContext()를 호출

5. 생성 Bean이 InitializingBean 인스턴스이면 afterProperties를 호출한다.

6. 설정 파일에 init-method가 존재한다면 init-method를 실행 

만약 Bean이 singleton이 아니라면 2번부터 초기화의 과정을 거치게된다.

## Bean Life Cycle custom
1. InitializingBean & DisposableBean 인터페이스를 이용해 custom
    - afterPropertiesSet()이나 destory()를 구현
    
2. xml설정
    - init-method와 destory-method 속성을 이용해 callBack Method를 지정한다.

3. Annotation
    - @PostConstruct 와 @PostDestory를 이용해 초기화 및 callback Method를 정의할수 있다.