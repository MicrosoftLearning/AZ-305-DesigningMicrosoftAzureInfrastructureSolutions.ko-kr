---
casestudy:
  title: 컴퓨팅 솔루션 디자인
  module: Compute solutions
---

# <a name="design-a-compute-solution"></a>컴퓨팅 솔루션 디자인

## <a name="requirements"></a>요구 사항

Tailwind Traders would like to migrate their product catalog application to the cloud. This application has a traditional 3-tier configuration using SQL Server as the data store. The IT team hopes you can help modernize the application. They have provided this diagram and several areas that could be improved. 

![컴퓨팅 아키텍처](media/compute.png)

* The frontend application is a .NET core-based web app. During peak periods 1750 customers visit the website each hour. 

* The application runs on IIS web servers in a front-end tier. This tier handles all customer requests for purchasing products. During the latest holiday sale, the front-end servers reached their performance limits and page loads were lengthy. The IT team has considered adding more servers, but during off hours the servers are often idle.

* The middle tier hosts the business logic that processes customer requests. These requests are often for help desk support. Support requests are queued and lately the wait times have been very long. Customers are offered email rather than wait for a representative. But many customers seem frustrated and are disconnecting rather than wait. Customer requests are 75-125 per hour. 

* Tailwind Traders는 제품 카탈로그 애플리케이션을 클라우드로 마이그레이션하려고 합니다.

* 고가용성이 중요하지만, 법적 요구 사항으로 인해 회사는 모든 리소스를 단일 지역에서 유지해야 합니다.

## <a name="tasks"></a>작업

* 이 애플리케이션에는 SQL Server를 데이터 저장소로 사용하는 기존의 3계층 구성이 있습니다. 

* IT 팀은 애플리케이션을 현대화하는 데 도움이 될 수 있기를 바랍니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
