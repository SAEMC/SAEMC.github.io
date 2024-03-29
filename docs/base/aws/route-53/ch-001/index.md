---
hide:
  - footer
---

# Route 53이란?

---

Amazon Route 53는 가용성과 확장성이 뛰어난 DNS(도메인 이름 시스템) 웹 서비스이다. Route 53을 사용하여 세 가지 주요 기능, 즉 도메인 등록, DNS 라우팅, 상태 확인을 조합하여 실행할 수 있다.

세 기능 모두에 Route 53을 사용하도록 선택한 경우 아래 순서를 따라야 한다.

1. 도메인 이름 등록

    웹 사이트의 이름(예: example.com)이 필요하다. Route 53을 통해 웹사이트 또는 웹 애플리케이션의 이름, 즉 도메인 이름을 등록할 수 있다.

2. 인터넷 트래픽을 도메인의 리소스로 라우팅

    사용자가 웹 브라우저를 열어 주소 표시줄에 도메인 이름(example.com) 또는 하위 도메인 이름(acme.example.com)을 입력한 경우 Route 53은 브라우저를 웹 사이트 또는 웹 애플리케이션에 연결하도록 돕는다.

3. 리소스의 상태 확인

    Route 53은 인터넷을 통해 웹 서버 같은 리소스로 자동화된 요청을 보내어 접근 및 사용이 가능하고 정상 작동 중인지 확인한다. 리소스를 사용할 수 없게 될 때 알림을 수신하고 비정상 리소스가 아닌 다른 곳으로 인터넷 트래픽을 라우팅할 수도 있다.

---

## References

- <https://docs.aws.amazon.com/ko_kr/Route53/latest/DeveloperGuide/Welcome.html>
