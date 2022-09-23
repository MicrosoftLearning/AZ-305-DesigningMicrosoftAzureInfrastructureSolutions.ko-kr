---
casestudy:
  title: 네트워크 솔루션 설계 -BI 엔터프라이즈 애플리케이션
  module: Network infrastructure solutions
---
# <a name="design-a-network-infrastructure-solution"></a>네트워크 인프라 솔루션 설계  

## <a name="requirements"></a>요구 사항

As the Tailwind Traders Enterprise IT team prepares to define the strategy to migrate some of company’s workloads to Azure, it must identify the required networking components and design a network infrastructure necessary to support them. Considering the global scope of its operations, Tailwind Traders will be using multiple Azure regions to host its applications. Most of these applications have dependencies on infrastructure and data services, which will also reside in Azure. Internal applications migrated to Azure must remain accessible to Tailwind Traders users. Internet-facing applications migrated to Azure must remain accessible to any external customer. 

초기 네트워킹 설계를 통합하기 위해 Tailwind Traders Enterprise IT 팀은 Azure로 마이그레이션해야 하는 가장 일반적인 워크로드 범주를 나타내는 두 가지 주요 애플리케이션을 선택했습니다.  

## <a name="design---bi-enterprise-application"></a>설계 - BI 엔터프라이즈 애플리케이션 

![BI 엔터프라이즈 애플리케이션 아키텍처](media/compute.png)

-   IIS 웹 서버를 실행하는 프런트 엔드 계층, .NET Framework 기반 비즈니스 논리를 호스팅하는 중간 계층, 그리고 SQL Server Always On 가용성 그룹 데이터베이스로 구현된 백엔드 계층이 있는 내부 Windows 기반의 3계층 BI(비즈니스 인텔리전스) 엔터프라이즈 애플리케이션입니다. 

-   이 애플리케이션은 중요 업무용으로 분류되며 가용성 SLA가 99.99%인 고가용성 프로비저닝과 10분 RPO와 2시간 RTO를 포함한 재해 복구 프로비저닝이 필요합니다.

-   To provide connectivity to internal apps migrated to Azure, Tailwind Traders will need to establish hybrid connectivity from their on-premises datacenters. The Enterprise IT group already established that such connectivity will be implemented by using ExpressRoute circuit from its main Seattle datacenter, however, at this point it is not clear yet what would be failover solution in case that circuit becomes unavailable. The Tailwind Traders CFO wants to avoid paying for another, redundant ExpressRoute circuit. 

- There are additional considerations that apply to on-premises connectivity to internal apps migrated to Azure. Since the Tailwind Traders Azure environment will consist of multiple subscriptions and, effectively, multiple virtual networks, to minimize cost, it is important to minimize the number of Azure resources required to implement core networking capabilities. Such capabilities include hybrid connectivity to on-premises locations as well as traffic filtering. Incidentally, this need to minimize cost aligns with the Information Security and Risk requirements, which state that all traffic between on-premises locations and Azure virtual networks must flow via a single virtual network, which will be hosting components responsible for hybrid connectivity and traffic filtering. 

-   As per requirements defined by the Tailwind Traders Information Security and Risk teams, all communication between Azure VMs in different tiers that are part of the same application must allow only the ports required to run and maintain the application. However, due to IP address space limitations, it might not be possible to allocate dedicated subnets to each tier. Enterprise IT group needs to identify the optimal way to configure source and destination for traffic filtering that would not require directly referencing IP addresses or IP address ranges.


## <a name="tasks---bi-enterprise-application"></a>작업 - BI 엔터프라이즈 애플리케이션 

1. Tailwind Traders Enterprise IT 팀은 회사의 워크로드 중 일부를 Azure로 마이그레이션하는 전략을 정의하기 위해 준비하는 동안 필요한 네트워킹 구성 요소를 식별하고 이를 지원하는 데 필요한 네트워크 인프라를 디자인해야 합니다. 

2. Tailwind Traders는 해당 작업의 전역 범위를 고려하여 애플리케이션을 호스트하는 여러 Azure 지역을 사용합니다. 

3. 스토리지(관계형) 사례 연구에 기반으로, 스토리지 계정에 대한 액세스를 보안하고 선택 사용자만 스토리지 계정에 액세스할 수 있도록 네트워크 설계를 업데이트하려면 어떻게 하나요?

4. SQL 백엔드의 현대화에 기반으로, 프런트 엔드가 코드 베이스에 하드 코딩된 비밀이 없도록 데이터베이스에 실용적인 액세스를 사용하도록 설정하려면 어떻게 해야 하나요?

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
