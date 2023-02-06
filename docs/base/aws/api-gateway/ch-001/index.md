---
hide:
  - footer
---

# API Gateway란?

---

Amazon API Gateway는 규모와 관계없이 REST 및 WebSocket API를 생성, 게시, 유지, 모니터링 및 보호하기 위한 AWS 서비스이다. API 개발자는 AWS 또는 다른 웹 서비스를 비롯해 [AWS 클라우드](http://aws.amazon.com/what-is-cloud-computing/)에 저장된 데이터에 액세스하는 API를 생성할 수 있다. API Gateway API 개발자는 자체 클라이언트 애플리케이션에서 사용할 API를 생성할 수 있다. 또는 타사 앱 개발자가 API를 사용하도록 제공할 수도 있다. 자세한 내용은 [API Gateway를 누가 사용하는가?](https://docs.aws.amazon.com/ko_kr/apigateway/latest/developerguide/api-gateway-overview-developer-experience.html#apigateway-who-uses-api-gateway) 단원을 참조한다.

API Gateway는 다음과 같은 RESTful API를 생성한다.

- HTTP 기반.

- 상태 비저장 클라이언트-서버 통신을 활성화한다.

- 표준 HTTP 메서드(예: GET, POST, PUT, PATCH, DELETE)를 구현한다.

API Gateway는 다음과 같은 WebSocket API를 생성한다.

- 클라이언트와 서버 간에 상태를 저장하는 전이중 통신을 지원하는 [WebSocket](https://tools.ietf.org/html/rfc6455) 프로토콜 준수.

- 수신 메시지를 메시지 콘텐츠에 따라 라우팅.

---

## References

- <https://docs.aws.amazon.com/ko_kr/apigateway/latest/developerguide/welcome.html>
