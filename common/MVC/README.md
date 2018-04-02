# MVC 패턴
하나의 어플리케이션을 Model, View, Controller로 나누어 구성하는것.

Model : 어플리케이션의 정보, 데이터등을 나타낸다.

View : 사용자가 눈으로 직접 보는 화면을 담당한다.

Controller : 지휘통제하는 역할이다.

Controller는 Model을 통해서 View로 데이터를 보내고, View에서 Model을 통해 데이터를 받아
처리하는 과정이다.

## 장점
유연하고 확장하기가 쉽다.
각각의 역할이 나누어져있기 때문에 유지보수나 확장시에 해당 부분만 고치면 된다.

## 단점
Model과 View의 분리가 쉽지않다.

## MVC1 vs MVC2
MVC1
```
    웹브라우저의 request를 JSP페이지가 전부 처리하는것
    JSP페이지에 비지니스 로직과 출력관리 코드가 모두 모여있다.
    JSP안에서 모든 정보를 표시하고 저장하고 처리하므로 재사용이 힘들고, 가독성이 떨어진다.
```    

MVC2
```
    MVC1 구조와는 다르게 웹브라우저의 Request를 Servlet이 받는다.
    Servlet은 Request를 처리 후 결과를 JSP에 출력한다.

```