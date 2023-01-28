---
hide:
  - footer
---

# 액세스 관리

---

AWS Identity and Access Management(IAM)은 AWS 리소스에 대한 액세스를 안전하게 제어할 수 있는 웹 서비스이다. 보안 주체가 AWS에 요청하면 AWS 적용 코드는 해당 보안 주체가 인증(로그인) 및 권한 부여(권한 있음)되었는지 확인한다. 정책을 생성하고 IAM 아이덴터티 또는 AWS 리소스에 연결하여 AWS 액세스를 관리한다. 정책은 아이덴터티 또는 리소스에 연결될 때 해당 권한을 정의하는 AWS의 JSON 정책 문서이다.

<figure markdown>
  ![001](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/images/access-diagram_800.png){ load=lazy }
</figure>

권한 부여 중 AWS 적용 코드는 요청 콘텍스트의 값을 사용하여 일치하는 정책을 확인하고 요청을 허용할지 거부할지 여부를 결정한다.

AWS은 요청 콘텍스트에 적용되는 각 정책을 확인한다. 단일 정책이 요청을 거부한 경우 AWS는 전체 요청을 거부하고 정책 평가를 중지한다. 이를 명시적 거부라고 한다. 요청은 기본적으로 거부되므로 IAM은 사용 가능한 정책이 요청의 모든 부분을 허용하는 경우에만 요청에 권한을 부여한다. 단일 계정 내 요청 평가 로직은 다음 규칙을 따른다.

- 기본적으로 모든 요청이 묵시적으로 거부된다. (또는 기본적으로 AWS 계정 루트 사용자에 모든 권한이 부여된다.)

- 아이덴터티 기반 또는 리소스 기반 정책에 포함된 명시적 허용은 이 기본 작동을 재정의한다.

- 권한 경계, 조직 SCP 또는 세션 정책이 있는 경우 이러한 정책 유형이 명시적 거부로 허용을 재정의할 수도 있다.

- 어떠한 정책의 명시적 거부도 허용을 무시한다.

요청이 인증 및 권한 부여된 후 AWS이 요청을 승인한다. 다른 계정에서 요청해야 하는 경우 다른 계정의 정책에서 요청자에게 해당 리소스에 대한 액세스를 허용해야 한다. 또한 요청하는 데 사용하는 IAM 엔터티에 해당 요청을 허용하는 아이덴터티 기반 정책이 있어야 한다.

---

## 1. 액세스 관리 리소스

권한 및 정책 생성에 대한 자세한 정보는 다음 리소스를 참조한다.

AWS 보안 블로그의 다음 게시물에서는 Amazon S3 버킷과 객체에 액세스하기 위한 정책을 작성하는 일반적인 방법을 소개한다.

- [IAM 정책 작성: Amazon S3 버킷에 대한 액세스 권한을 부여하는 방법](http://aws.amazon.com/blogs/security/writing-iam-policies-how-to-grant-access-to-an-amazon-s3-bucket/)

- [IAM 정책 작성: Amazon S3 버킷의 사용자별 폴더에 대한 액세스 권한 부여](http://aws.amazon.com/blogs/security/writing-iam-policies-grant-access-to-user-specific-folders-in-an-amazon-s3-bucket/)

- [IAM 정책 및 버킷 정책과 ACLs! ACL (S3 리소스에 대한 액세스 제어)](http://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/)

- [RDS 리소스 수준 권한에 대한 소개](http://aws.amazon.com/blogs/security/a-primer-on-rds-resource-level-permissions)

- [EC2 리소스 수준 권한 설명](http://aws.amazon.com/blogs/security/demystifying-ec2-resource-level-permissions/)

---

## References

- <https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/access.html>
