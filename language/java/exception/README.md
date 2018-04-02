# Exception class
Java에서 예외처리를 담당하는 class이다.

Java에서 에러는 시스템내부에서 발생하는 심각한 수준의 오류를 에러라고 칭한다.
개발자가 미리 예측하지 못하기 때문에 애플리케이션에서 처리하지 않아도 된다.

Exception은 크게 두가지 경우로 나눌수있습니다.

checked Exception 과 unchecked Exception으로 나눌수있습니다.

두가지의 가장 큰 차이점은 컴파일러의 check유무입니다.

checked Exception은 컴파일러가 체크하여 예외처리를 try catch구문이나 throws를 통해 예외를 처리하는 코드를 작성하게합니다.
Exception이 발생했을때 roll-back되지 않습니다.

unchecked Exception은 컴파일러가 체크하지 않아 예외처리를 코드내부에 구현하지않아도 실행 가능합니다.
Exception이 발생시 roll-back이 됩니다.

Exception class는 checked Exception 이며, RunTimeException class는 unchecked Exception입니다.
