# BigDecimal
일반적으로 정수인 경우 int형이면 충분히 표현이 가능하다.

소수점이 포함되더라도 double형이면 일반적인 표현이 가능하다.

하지만 무한대로 커지거나 상세한 표현이 필요한 숫일때는 int와 double은 적절하지 않을수 있다.

특히 화폐를 다룰때는 double이나 int는 최악의 선택이 될수있다.

int나 double은 표현할수 있는 한계치가 존재한다. 

만약 표현할수 있는 한계치보다 초과하거나 미만이라면 정확한 결과가 나올수가 없다.

double형이나 float형에서는 출력된 결과가 오차값을 가질수있다.

오차값을 가지는 이유는 특정 10진수를 2진수만으로 표현하는것이 불가능하기 때문이다.

예를들어 0.1은 2진수로 완벽하게 표현하지 못한다.

소수점을 2진수로 계산한다면 0.1은 00011이 반복된다.

계속 반복되는 자리수이기 때문에 2진수로 정확히 표현할수가 없다.

이렇게 때문에 double이나 float형은 가장 근사값을 표현하게 된다.

만약 기본 자료형을 사용해 화폐를 표현하고 싶다면 double과 float형이 아닌 int와 long형태를 사용하고 출력시에만 소수점으로 바꾸어 출력해서 사용해야 한다.

이러한 결과값을 예방하기 위해서는 BigInteger와 BigDecimal이 존재한다.

하지만 BigInteger는 정수를 표현하고 BigDecimal은 실수를 다룬다.

BigInteger는 이진수 계산이 아닌 십진수 소수 계산을 제공한다.

이떄 화폐의 경우 실수까지 표현해야 하므로 BigDecimal이 적절하다.

BigDecimal과 BigInteger는 산술연산자를 이용한 연산은 지원하지 않지만 Method를 이용해 계산을 할수있다.

BigDecimal이 실수연산에 더 적합한 이유는 반올림을 확실히 제어할수 있다.