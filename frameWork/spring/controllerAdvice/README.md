# ControllerAdvice
스프링에서 사용가능한 어노테이션이다.

ControllerAdvice 어노테이션을 붙인 클래스들은 추후 생기는 Exception을 catch하는 기능을 가지고 있다.

내부에서 Exception을 catch하는 방법은

```
    @ExceptionHandler(value = 처리할 Exception class.class)
    public void exceptionHandler(처리할Exception class e){
    
    }

```

위와 같은 방식으로 @ExceptionHandler를 처리하는 메소드를 만들어 주면 된다.

리턴값은 void부터 ModelAndView까지 다양하게 선언 가능하다.

### ControllerAdvice를 사용해야하는이유
ControllerAdvice를 사용하는 이유는 2가지 라고 생각한다.

1. 예외처리를 한곳에 묶어서 편하게 가능하다.
    특정한 경우 예외처리를 담당하는 클래스를 생성하고 그 클래스를 ExceptionHandler에 등록해준다면
    이곳에서 특정 예외처리를 모두 담당할수있다.
    
2. 예외가 발생했을때 stack Message를 노출하지 않기 위해서이다.
    개발도중에 stack Message는 오히려 예외를 처리할수 있는 좋은 예시가 되지만
    운영도중에 stack Message를 그대로 노출하는것은 치명적인 단점이고 보안에도 취약할수있다.
    그렇기 때문에 ControllerAdvice를 사용해 예측하지 못한 상황에서 모든 예외상황을
    처리하는 것이다.