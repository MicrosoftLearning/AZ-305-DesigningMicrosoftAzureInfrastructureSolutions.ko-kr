
# <a name="design-a-network-infrastructure-solution"></a>네트워크 인프라 솔루션 설계  

## <a name="requirements"></a>요구 사항

As the Tailwind Traders Enterprise IT team prepares to define the strategy to migrate some of company’s workloads to Azure, it must identify the required networking components and design a network infrastructure necessary to support them. Considering the global scope of its operations, Tailwind Traders will be using multiple Azure regions to host its applications. Most of these applications have dependencies on infrastructure and data services, which will also reside in Azure. Internal applications migrated to Azure must remain accessible to Tailwind Traders users. Internet-facing applications migrated to Azure must remain accessible to any external customer. 

초기 네트워킹 설계를 통합하기 위해 Tailwind Traders Enterprise IT 팀은 Azure로 마이그레이션해야 하는 가장 일반적인 워크로드 범주를 나타내는 두 가지 주요 애플리케이션을 선택했습니다.  

### <a name="design---product-catalog-enterprise-application"></a>설계 - 제품 카탈로그 엔터프라이즈 애플리케이션

![제품 카탈로그 아키텍처](media/catalog.png)

- An internet-facing, Windows-based two-tier .NET Core-based web app providing access to the product catalog, hosted in a SQL Server Always On Availability Group database. This application is categorized as mission-critical, with availability SLA of 99.99%, 10-minute RPO and 2-hour RTO. 

-   Business leads emphasize the importance of the optimal customer experience when accessing internet-facing apps, so it is critical that the time it takes to load web pages and download static content is minimized. Similarly, a failure of individual servers hosting web app components and their dependencies should have negligible impact on the web app availability perceived by customers. While it’s understood that a regional failure might introduce some interruption to existing web sessions, the failover to a disaster recovery site should be automatic.

- Azure PaaS 서비스에서 제공하는 이점을 활용하기 위해 Enterprise IT 팀은 Azure SQL Database를 사용하여 제품 카탈로그 엔터프라이즈 애플리케이션의 데이터베이스를 구현하기로 결정했습니다. 

- Tailwind Traders 정보 보안 및 위험 팀은 동일한 애플리케이션의 일부인 Azure VM과 PaaS 서비스 간의 모든 통신이 PaaS 서비스의 퍼블릭 엔드포인트를 통하지 않고 Azure 백본을 통해 이동해야 합니다. 

## <a name="tasks---product-catalog-enterprise-application"></a>작업 - 제품 카탈로그 엔터프라이즈 애플리케이션

1. Tailwind Traders Enterprise IT 팀은 회사의 워크로드 중 일부를 Azure로 마이그레이션하는 전략을 정의하기 위해 준비하는 동안 필요한 네트워킹 구성 요소를 식별하고 이를 지원하는 데 필요한 네트워크 인프라를 디자인해야 합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?

