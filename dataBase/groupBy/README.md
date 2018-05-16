# GroupBy
데이터들을 원하는 그룹으로 분류할때 사용된다.

나누고자 하는 그룹의 컬럼명을 groupBy에 써준다.

## Distinct vs GroupBy
두가지 키워드의 차이점은 

Distinct는 unique한 값을 얻어내기 위한 키워드이다.

하지만 groupBy는 테이터를 그룹핑하는 역할을 담당한다.

두개의 결과값이 비슷해보이지만 전혀 다른 개념이다.

## Having
Where 절에서는 집계함수를 사용할수 없다.

Having은 집계함수를 가지고 조건비교를 할때 사용 가능하다.

Having은 groupBy절과 함께 사용가능하다.