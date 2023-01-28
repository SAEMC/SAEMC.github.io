---
hide:
  - footer
---

# 시작하기

---

이 항목에서는 AWS 계정에서 AWS Identity and Access Management(IAM) 사용자를 생성하여 AWS 리소스에 대한 액세스 권한을 부여하는 방법을 보여준다. 먼저 그룹이나 사용자를 생성하기 전에 알고 있어야 할 IAM 개념 몇 가지에 대해 학습한 후 AWS Management Console을 사용해 필요한 작업을 실행하는 방법에 대해 알아볼 것이다. 첫 번째 작업은 AWS 계정에 관리자 그룹을 구성하는 방법이다. AWS 계정의 관리자 그룹은 필수는 아니지만 강력히 권장하는 구성이다.

아래 그림은 AWS 계정을 3개 그룹으로 구성한 간단한 예이다. 하나는 책임이 비슷한 사용자들을 모아놓은 그룹이다. 이 예에서는 관리자 그룹(*Admins*라고 표시된 그룹)에 해당한다. 그 밖에도 *Developers* 그룹과 *Test* 그룹이 있다. 각 그룹은 사용자가 다수이다. 그리고 그림과 다르지만 각 사용자는 하나 이상의 그룹에 속할 수 있다. 하지만 그룹이 다른 그룹에 포함될 수는 없다. 이제 정책을 사용하여 권한을 그룹에게 부여한다.

<figure markdown>
  ![001](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/Account_Group_Example.diagram.png){ load=lazy }
</figure>

다음 절차에서는 아래 작업을 실행하게 된다.

- Administrators 그룹을 생성한 후 AWS 계정의 모든 리소스에 액세스할 수 있는 권한을 그룹에게 부여한다.
- 직접 사용자를 생성하여 Administrators 그룹에 추가한다.
- AWS Management Console에 로그인할 수 있도록 사용자 암호를 생성한다.

유효한 모든 AWS 계정 리소스에 액세스할 수 있는 권한을 Administrators 그룹에게 부여한다. 여기에서 유효한 리소스란 사용 중이거나 등록한 모든 AWS 제품을 의미한다. Administrators 그룹 사용자는 AWS 계정의 보안 크레덴셜만 제외하고 AWS 계정 정보에 액세스할 수 있다.

---

## References

- <https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/getting-started.html>
