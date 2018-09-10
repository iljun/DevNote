# IAM
AWS는 인스턴스가 구성되고 완료된 순간부터 과금이 시작된다.

과금의 요소를 제외하고도 인스턴스의 생성과 관리의 권한은 매우 중요하다.

IAM은 바로 요청을 보낸 사용자를 관리하고 적절한 권한을 가지고있는지 식별하는 권한체계이다.

IAM은 AWS 인스턴스, IAM으로 생성된 계정의 Authentication과 Authorization을 담당한다.

IAM을 통해 생성한 계정과 하나하나의 리소스들에 대해서도 각각 독립적인 권한관리를 가능하게 하는것이 IAM이다.

## IAM에서 사용하는 객체 

IAM의 객체는 크게 두가지 영역으로 나뉜다.

하나는 사용자를 정의하는 객체, 다른 하나는 권한을 정의하는 객체이다.

사용자를 정의하는 객체는 IAM User, IAM Group, IAM Role

각 사용자의 권한을 정의하는 IAM Policy

사용자와 권한은 1:N으로 매핑되며 IAM User + IAM Policy or IAM Group + IAM Policy or IAM Role + IAM Policy 등으로 사용이 가능하다.

### IAM User
AWS 계정을 처음 생성하면 생기는 계정이 바로 ROOT 계정이다.

이 ROOT 계정과 추가로 생겨난 계정을 모두다 IAM User이다.

흔히 하나의 서버를 구성하더라고 ROOT 계정을 개발자, 네트워크 담당자, 보안 담당자 등등등 여러 직군의 사람들이 사용하지는 않는다.

이러한 개념으로 ROOT 계정 이외로 IAM User로 각각의 사용자의 계정을 생성 가능하고 권한을 조정할수 있다.

#### IAM User 인증 방식
1. AWS Management Console username/password
2. AWS CLI, AWS SDK AccessKey/SecrectKey

### IAM Group
IAM User를 생성해서 권한을 부여했다.

하지만 같은 직군의 사람들이 늘어날때마다 계정을 생성하고 일일이 권한을 부여해야할까?

이런 일을 방지하기 위한것이 바로 IAM Group이다.

쉽게 IAM User들을 단위로 묶어 관리하기 위한것이 IAM Group이다.

IAM Group을 사용하게 된다면 동일한 권한이 필요한 IAM User들을 묶어놓고

IAM Group에 권한을 부여해서 사용 가능하다.

### IAM Policy
IAM User나 IAM Group에 정의되는 권한이다.

### IAM ROLE
AWS 서비스간 권한을 제어하거나 외부 서비스의 권한을 제어할때 사용한다.

또는 AWS 인스턴스의 접근, 생성, 삭제 등의 권한을 나타낸다.

IAM ROLE은 직접 IAM User나 IAM Group에 적용되지 않고 IAM Policy에 적용된다.
