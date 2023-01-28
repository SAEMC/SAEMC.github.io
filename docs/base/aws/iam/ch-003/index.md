---
hide:
  - footer
---

# AWS에 로그인

---

AWS Management Console에서는 AWS 리소스를 생성하고 관리하는 데 사용할 수 있는 웹 기반 사용자 인터페이스를 제공한다. 예를 들어 Amazon EC2 인스턴스를 시작 및 중지하고, Amazon DynamoDB 테이블을 생성하고, Amazon S3 버킷을 생성하는 등의 작업을 수행할 수 있다.

AWS Management Console을 사용하려면 먼저 AWS 계정에 로그인해야 한다. AWS 계정에 로그인하는 데 사용하는 프로세스는 AWS 사용자 유형에 따라 다르다. AWS에는 두 가지 유형의 사용자가 있다. 계정 소유자(루트 사용자)이거나 IAM 사용자이다. 계정을 생성하는 데 사용된 이메일 주소와 암호를 사용하여 AWS 계정을 생성할 때 루트 사용자가 생성된다. IAM 사용자는 루트 사용자 또는 AWS 계정 내의 IAM 관리자가 생성한다.

---

## 1. 루트 사용자로 로그인

루트 사용자로 AWS 계정에 로그인하기 전에 다음과 같은 필수 정보가 있는지 확인한다.

**요구 사항**

- AWS 계정을 생성하는 데 사용되는 이메일 주소

- 루트 사용자의 암호

**루트 사용자로 AWS 계정에 로그인하려면**

1. <https://console.aws.amazon.com/>을 연다.

2. 이전에 이 브라우저를 사용하여 로그인하지 않은 경우 기본 로그인 페이지가 다음과 같이 나타난다. **루트 사용자(Root user)**를 선택하고 계정과 연결된 이메일 주소를 입력한 후 **다음(Next)**을 선택한다.

    <figure markdown>
      ![001](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/sign-in-main-capture.png){ load=lazy }
    </figure>

    이전에 이 브라우저를 사용하여 루트 사용자로 로그인한 경우 브라우저가 AWS 계정의 이메일 주소를 기억할 수 있다. 이 경우 대신 다음 단계에서 표시된 화면이 나타난다.

    이전에 이 브라우저를 사용하여 IAM 사용자로 로그인한 경우 대신 브라우저에 IAM 사용자 로그인 페이지가 표시될 수 있다. 기본 로그인 페이지로 돌아가려면 **루트 사용자 이메일을 사용하여 로그인(Sign in using root user email)**을 선택한다.

3. 암호를 입력하고 로그인을 선택한다.

    <figure markdown>
      ![002](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/sign-in-root-user-capture.png){ load=lazy }
    </figure>

---

## 2. IAM 사용자로 로그인

IAM 사용자로 AWS 계정에 로그인하기 전에 다음과 같은 필수 정보가 있는지 확인한다. 이 정보가 없으면 AWS 계정의 관리자에게 문의한다.

**요구 사항**

- 다음 중 하나이다.

      - 계정 별칭

      - 12자리 AWS 계정 ID

- IAM 사용자의 사용자 이름

- IAM 사용자의 암호

IAM 사용자인 경우 로그인 URL 또는 기본 로그인 페이지를 사용하여 로그인할 수 있다.

**IAM 사용자 로그인 URL을 사용하여 IAM 사용자로 AWS 계정에 로그인하려면**

1. 브라우저를 열고 다음 로그인 URL을 입력한다. 이때 `account_alias_or_id`를 관리자가 제공한 계정 별칭 또는 계정 ID로 바꾼다.

    ```
    https://account_alias_or_id.signin.aws.amazon.com/console/
    ```

2. IAM 사용자 이름과 암호를 입력하고 **로그인**을 선택한다.

    <figure markdown>
      ![003](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/sign-in-iam-user-capture.png){ load=lazy }
    </figure>

**기본 로그인 페이지를 사용하여 IAM 사용자로 AWS 계정에 로그인하려면**

1. <https://console.aws.amazon.com/>을 연다.

2. 이전에 이 브라우저를 사용하여 로그인하지 않은 경우 기본 로그인 페이지가 나타난다. **IAM 사용자(IAM user)**를 선택하고 계정 별칭 또는 계정 ID를 입력한 후 **다음(Next)**을 선택한다.

    <figure markdown>
      ![004](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/sign-in-main-capture-iam.png){ load=lazy }
    </figure>

    이전에 이 브라우저를 사용하여 IAM 사용자로 로그인한 경우 브라우저가 AWS 계정의 계정 별칭 또는 계정 ID를 기억할 수 있다. 이 경우 대신 다음 단계에서 표시된 화면이 나타난다.

3. IAM 사용자 이름과 암호를 입력하고 **로그인**을 선택한다.

    <figure markdown>
      ![005](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/sign-in-iam-user-capture.png){ load=lazy }
    </figure>

    이전에 이 브라우저를 사용하여 다른 AWS 계정의 IAM 사용자로 로그인했거나 대신 루트 사용자로 로그인해야 하는 경우 루트 사용자 **이메일을 사용하여 로그인(Sign in using root user email)**을 선택하여 기본 로그인 페이지로 돌아간다.

---

## References

- <https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/console.html>
