---
hide:
  - footer
---

# CloudFront란?

---

Amazon CloudFront는 .html, .css, .js 및 이미지 파일과 같은 정적 및 동적 웹 콘텐츠를 사용자에게 더 빨리 배포하도록 지원하는 웹 서비스이다. CloudFront는 엣지 로케이션이라고 하는 데이터 센터의 전 세계 네트워크를 통해 콘텐츠를 제공한다. CloudFront를 통해 서비스하는 콘텐츠를 사용자가 요청하면 지연 시간이 가장 낮은 엣지 로케이션으로 요청이 라우팅되므로 가능한 최고의 성능으로 콘텐츠가 제공된다.

- 콘텐츠가 이미 지연 시간이 가장 낮은 엣지 로케이션에 있는 경우 CloudFront가 콘텐츠를 즉시 제공한다.

- 콘텐츠가 엣지 로케이션에 없는 경우 CloudFront는 콘텐츠의 최종 버전에 대한 소스로 지정된 오리진(Amazon S3 버킷, MediaPackage 채널, HTTP 서버(예: 웹 서버) 등)에서 콘텐츠를 검색한다.

예를 들어, CloudFront가 아닌 일반적인 웹 서버에서 이미지를 제공한다고 가정한다. 예를 들어 `https://example.com/sunsetphoto.png` URL을 사용하여 sunsetphoto.png라는 이미지를 서비스할 수 있다.

사용자는 이 URL로 쉽게 이동해 해당 이미지를 볼 수 있다. 하지만 이미지가 발견될 때까지 인터넷으로 이루어진 상호 연결된 네트워크의 복잡한 모음을 통해 네트워크에서 다른 네트워크로 요청이 라우팅되었다는 사실은 아마도 모르고 있을 것이다.

CloudFront는 AWS 백본 네트워크를 통해 콘텐츠를 가장 효과적으로 서비스할 수 있는 엣지로 각 사용자 요청을 라우팅하여 콘텐츠 배포 속도를 높인다. 일반적으로 CloudFront 엣지가 최종 사용자에게 가장 빨리 제공한다. AWS 네트워크를 사용하면 사용자의 요청이 반드시 통과해야 하는 네트워크의 수가 줄어들어 성능이 향상된다. 파일의 첫 바이트를 로드하는 데 걸리는 지연 시간이 줄어들고 데이터 전송 속도가 빨라진다.

또한 파일(객체라고도 함)의 사본이 전 세계 여러 엣지 로케이션에 유지(또는 캐시)되므로 안정성과 가용성이 향상된다.

---

## 1. 콘텐츠를 전송하도록 CloudFront를 설정하는 방법

CloudFront 배포를 생성하여 CloudFront에 어디로부터 콘텐츠를 전송하고자 하는지와 이러한 콘텐츠 전송을 추적 및 관리하는 방법에 대한 세부 정보를 알린다. 그런 다음 CloudFront는 최종 사용자와 인접한 컴퓨터(엣지 서버)를 사용하여 사용자가 콘텐츠를 사용하거나 보고자 할 때 빠르게 전송한다.

<figure markdown>
  ![001](https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/images/how-you-configure-cf.png){ load=lazy }
</figure>

**콘텐츠를 전송하도록 CloudFront를 구성하는 방법**

1. Amazon S3 버킷 또는 고유 HTTP 서버와 같은 오리진 서버를 지정하고, CloudFront는 이로부터 파일을 가져온 다음 전 세계 CloudFront 엣지 로케이션에 배포한다.

    오리진 서버는 객체의 최종 원본 버전을 저장한다. HTTP를 통해 콘텐츠를 서비스하는 경우 오리진 서버가 Amazon S3 버킷 또는 웹 서버 같은 HTTP 서버이다. HTTP 서버는 Amazon Elastic Compute Cloud(Amazon EC2) 인스턴스나 사용자가 관리하는 서버에서 실행할 수 있다. 이 서버를 사용자 지정 오리진이라고도 한다.

2. 오리진 서버에 파일을 업로드한다. 객체라고도 하는 파일은 일반적으로 웹 페이지, 이미지 및 미디어 파일을 포함하지만 HTTP를 통해 제공될 수 있는 모든 항목이 될 수 있다.

    Amazon S3 버킷을 오리진 서버로 사용할 경우 버킷에 있는 객체를 공개적으로 읽을 수 있는 상태로 만들 수 있으므로 객체의 CloudFront URL을 아는 사람이라면 누구나 액세스할 수 있다. 객체를 비공개로 유지하고 액세스할 수 있는 사용자를 제어할 수 있는 옵션도 있다. [서명된 URL과 서명된 쿠키를 사용하여 프라이빗 콘텐츠 제공](https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html)을(를) 참조한다.

3. 사용자가 웹 사이트나 애플리케이션을 통해 파일을 요청할 경우 CF에 어떤 오리진 서버에서 파일을 가져올지 알려 주는 CloudFront 배포를 만든다. 동시에 CloudFront에서 모든 요청을 기록할지, 배포를 만들자마자 활성화할지 여부와 같은 세부 사항을 지정한다.

4. CloudFront는 새 배포에 도메인 이름을 할당하고, 이는 CloudFront 콘솔에서 볼 수 있다. 또는 API 요청 등과 같은 프로그램 요청에 대한 응답으로 반환된다. 원하는 경우 대신 사용할 대체 도메인 이름을 추가할 수 있다.

5. CloudFront에서는 배포의 구성(사용자의 콘텐츠가 아님)을 모든 해당 엣지 로케이션 또는 CloudFront가 파일의 사본을 캐싱하는 지리적으로 분산된 데이터 센터의 POP(Point of Presence) 서버 모음으로 보낸다.

웹 사이트 또는 애플리케이션을 개발할 경우 CloudFront가 URL에 제공하는 도메인 이름을 사용한다. 예를 들어, CloudFront가 `d111111abcdef8.cloudfront.net`을 배포의 도메인 이름으로 반환할 경우 Amazon S3 버킷(또는 HTTP 서버의 루트 디렉터리)에 있는 logo.jpg의 URL이 `https://d111111abcdef8.cloudfront.net/logo.jpg`가 된다.

또는 CloudFront를 설정하여 고유한 도메인 이름을 배포와 사용할 수도 있다. 이 경우 URL이 `https://www.example.com/logo.jpg`가 될 수 있다.

또는 파일에 머리글을 추가하도록 오리진 서버를 구성할 수 있다. 이는 CloudFront 엣지 로케이션의 캐시에 파일을 얼마나 오래 보관할지 나타낸다. 기본적으로 각 파일은 만료되기 전에 24시간 동안 엣지 로케이션에 남아 있다. 최소 만료 시간은 0초이며, 최대 만료 시간은 없다. 자세한 내용은 [콘텐츠가 캐시에 유지되는 기간(만료) 관리](https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/Expiration.html) 단원을 참조한다.

---

## References

- <https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/Introduction.html>
