---
casestudy:
  title: 네트워크 솔루션 설계 -BI 엔터프라이즈 애플리케이션
  module: Network infrastructure solutions
ms.openlocfilehash: a31df2ef4ef67fddbce5d84922176f39fe326c2d
ms.sourcegitcommit: 0398c15157de2f621dd945e76523b824e500901c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "139134234"
---
# <a name="design-a-network-infrastructure-solution"></a>네트워크 인프라 솔루션 설계  

예상 시간: 60분

## <a name="requirements"></a>요구 사항

Tailwind Traders Enterprise IT 팀은 회사의 워크로드 중 일부를 Azure로 마이그레이션하는 전략을 정의하기 위해 준비하는 동안 필요한 네트워킹 구성 요소를 식별하고 이를 지원하는 데 필요한 네트워크 인프라를 디자인해야 합니다. Tailwind Traders는 해당 작업의 전역 범위를 고려하여 애플리케이션을 호스트하는 여러 Azure 지역을 사용합니다. 이러한 애플리케이션은 대부분 인프라 및 데이터 서비스에 대한 종속성이 있으며, Azure에도 상주합니다. Azure로 마이그레이션된 내부 애플리케이션은 Tailwind Traders 사용자가 계속 액세스할 수 있어야 합니다. Azure로 마이그레이션된 내부 애플리케이션은 외부 고객이 계속 액세스할 수 있어야 합니다. 

초기 네트워킹 설계를 통합하기 위해 Tailwind Traders Enterprise IT 팀은 Azure로 마이그레이션해야 하는 가장 일반적인 워크로드 범주를 나타내는 두 가지 주요 애플리케이션을 선택했습니다.  

## <a name="design---bi-enterprise-application"></a>설계 - BI 엔터프라이즈 애플리케이션 

![BI 엔터프라이즈 애플리케이션 아키텍처](media/compute.png)

-   IIS 웹 서버를 실행하는 프런트 엔드 계층, .NET Framework 기반 비즈니스 논리를 호스팅하는 중간 계층, 그리고 SQL Server Always On 가용성 그룹 데이터베이스로 구현된 백엔드 계층이 있는 내부 Windows 기반의 3계층 BI(비즈니스 인텔리전스) 엔터프라이즈 애플리케이션입니다. 

-   이 애플리케이션은 중요 업무용으로 분류되며 가용성 SLA가 99.99%인 고가용성 프로비저닝과 10분 RPO와 2시간 RTO를 포함한 재해 복구 프로비저닝이 필요합니다.

-   Azure로 마이그레이션된 내부 앱에 대한 연결을 제공하려면 Tailwind Traders가 온-프레미스 데이터 센터에서 하이브리드 연결을 설정해야 합니다. Enterprise IT 그룹은 이미 주 시애틀 데이터 센터의 ExpressRoute 회로를 사용하여 이러한 연결을 구현할 것이라고 설정했습니다. 그러나 이 시점에서 회로를 사용할 수 없게 될 경우 장애 조치(failover) 솔루션이 무엇인지는 아직 명확하지 않습니다. Tailwind Traders CFO는 다른 중복 ExpressRoute 회로에 대한 비용을 지불하지 않으려고 합니다. 

- Azure로 마이그레이션된 내부 앱에 대한 온-프레미스 연결에 적용되는 추가 고려 사항이 있습니다. Tailwind Traders Azure 환경은 비용을 최소화하기 위해 여러 구독과 여러 가상 네트워크로 효과적으로 구성되므로, 핵심 네트워킹 기능을 구현하는 데 필요한 Azure 리소스 수를 최소화하는 것이 중요합니다. 이러한 기능에는 트래픽 필터링뿐만 아니라 온-프레미스 위치에 대한 하이브리드 연결도 포함됩니다. 또한 이 작업은 온-프레미스 위치와 Azure 가상 네트워크 간의 모든 트래픽이 하이브리드 연결 및 트래픽 필터링을 담당하는 구성 요소를 호스팅할 단일 가상 네트워크를 통해 전달되어야 한다는 정보 보안 및 위험 요구 사항과 일치하는 비용을 최소화해야 합니다. 

-   Tailwind Traders 정보 보안 및 위험 팀에서 정의한 요구 사항에 따라, 동일한 애플리케이션의 일부인 서로 다른 계층의 Azure VM 간 모든 통신은 애플리케이션을 실행하고 유지 관리하는 데 필요한 포트만 허용해야 합니다. 그러나 IP 주소 공간 제한으로 인해 각 계층에 전용 서브넷을 할당하지 못할 수 있습니다. Enterprise IT 그룹은 IP 주소 또는 IP 주소 범위를 직접 참조할 필요가 없는 트래픽 필터링을 위한 원본과 대상을 구성하는 최적의 방법을 식별해야 합니다.


## <a name="tasks---bi-enterprise-application"></a>작업 - BI 엔터프라이즈 애플리케이션 

1. BI 애플리케이션에 대한 3계층 네트워크 솔루션을 설계합니다. 설계에 Azure ExpressRoute, VPN Gateway, Application Gateway, Azure Firewall 및 Azure Load Balancer를 포함할 수 있습니다. 네트워킹 구성 요소를 가상 네트워크로 그룹화해야 하며 네트워크 보안 그룹을 고려해야 합니다. 솔루션의 각 구성 요소를 선택한 이유를 설명할 준비를 합니다. 

2. 컴퓨팅 사례 연구의 설계자 솔루션을 기반으로, 이것은 네트워크 설계에 어떤 영향을 주나요? 현대화된 애플리케이션에 대한 액세스를 보호하기 위해 추가 네트워킹 리소스가 필요한가요? 원래 네트워크 설계에서 구현된 권장 솔루션 중 일부가 더 이상 필요하지 않은가요? 

3. 스토리지(관계형) 사례 연구에 기반으로, 스토리지 계정에 대한 액세스를 보안하고 선택 사용자만 스토리지 계정에 액세스할 수 있도록 네트워크 설계를 업데이트하려면 어떻게 하나요?

4. SQL 백엔드의 현대화에 기반으로, 프런트 엔드가 코드 베이스에 하드 코딩된 비밀이 없도록 데이터베이스에 실용적인 액세스를 사용하도록 설정하려면 어떻게 해야 하나요?

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
