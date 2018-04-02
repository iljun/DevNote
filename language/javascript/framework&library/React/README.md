# React
View를 컴포넌트로 구분해 개발하고, 이를 관리하기위한 Library이다.

## 특징 3가지

### JUST THE UI
React.js는 UI를 만들기위한 Library입니다.
다른 js FrameWork와는 다르게 UI부분만 담당한다.

### VirtualDom
JavaScript 내부에 DomTree와 같은 구조체인 VirtualDom을 가지고있어
Dom을 다시 그릴때는 변경점만을 찾아 최소한의 변경점만 변경해 빠른 속도를 가지고있다.

### Data Flow
단방향 데이터 흐름을 지향한다.

Application의 데이터를 관리하는 모델 컴포넌트가 존재하고, 이 데이터를 UI 컴포넌트로 전달하는
단순한 흐름이기 떄문에 이해하기 쉽고 빠르게 개발 가능하다.