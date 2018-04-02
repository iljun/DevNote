# BackBone
Model-View 구조로 모듈화할수 있도록 해주는 FrameWork

기본적으로 MCVR(Model-Collection-Views-Routers)의 구조를 가지고있다.

### Model
개별 데이터를 의미한다.

### Collections
Model들의 집합이며,
view와 연결되어있어 Model에 변화가 생길시 손쉽게 View를 갱신할수있다.

### Views
화면에 나타나는 UI 및 프론트엔드의 특성을 가진다.
Controller의 역할과 비슷한 면이 있다.

### Router
location.href에 따른 변경처리를 담당한다.
Controller의 성격이 가지고있다.
