---
hide:
  - footer
---

# 시작하기

---

Amazon Route 53로 도메인을 등록하고 정적 웹 사이트로 확인하는 DNS 쿼리에 응답하도록 Route 53를 구성하여 기본 단계를 시작한다. 첫 번째 자습서에서는 오픈 Amazon S3 버킷에서 정적 웹 사이트를 호스팅하고, 두 번째 자습서에서는 Amazon CloudFront 배포를 사용하여 SSL/TLS를 웹 사이트에 제공한다.

**추정 비용**

- 도메인을 등록 연간 요금은 9달러부터 시작하여 .com 등의 최상위 도메인의 경우에는 수백 달러까지 다양하다. 자세한 내용은 [Route 53 도메인 등록 요금](https://d32ze2gidvkk54.cloudfront.net/Amazon_Route_53_Domain_Registration_Pricing_20140731.pdf)을 참조한다. 이 요금은 환불되지 않는다.

- 도메인을 등록하면 도메인과 동일한 이름의 호스팅 영역이 자동으로 생성된다. 호스팅 영역을 사용하여 Route 53가 도메인의 트래픽을 라우팅할 장소를 지정할 수 있다.

- 이 자습서에서는 Amazon S3 버킷을 생성하고 샘플 웹 페이지를 업로드한다. AWS를 처음 사용하는 고객인 경우 Amazon S3를 무료로 시작할 수 있다. 기존 AWS 고객인 경우, 저장하는 데이터 양, 데이터 요청 횟수, 전송되는 데이터 양에 따라 요금이 청구된다. 자세한 내용은 [Amazon S3 요금](http://aws.amazon.com/s3/pricing/)을 참조한다.

- CloudFront 요금은 데이터 요청 횟수, 사용하는 엣지 로케이션 수, 전송되는 데이터 양에 따라 청구된다. 자세한 내용은 [CloudFront 요금](http://aws.amazon.com/cloudfront/pricing/)을 참조한다.

---

## References

- <https://docs.aws.amazon.com/ko_kr/Route53/latest/DeveloperGuide/getting-started.html>
