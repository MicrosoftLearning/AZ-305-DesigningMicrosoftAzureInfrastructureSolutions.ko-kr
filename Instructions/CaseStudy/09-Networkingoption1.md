---
ms.openlocfilehash: 3a9b3c04c88b0a683600ff83229abe631961c356
ms.sourcegitcommit: 0398c15157de2f621dd945e76523b824e500901c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2022
ms.locfileid: "139134235"
---

# <a name="design-a-network-infrastructure-solution"></a>네트워크 인프라 솔루션 설계  

예상 시간: 60분

## <a name="requirements"></a>요구 사항

Tailwind Traders Enterprise IT 팀은 회사의 워크로드 중 일부를 Azure로 마이그레이션하는 전략을 정의하기 위해 준비하는 동안 필요한 네트워킹 구성 요소를 식별하고 이를 지원하는 데 필요한 네트워크 인프라를 디자인해야 합니다. Tailwind Traders는 해당 작업의 전역 범위를 고려하여 애플리케이션을 호스트하는 여러 Azure 지역을 사용합니다. 이러한 애플리케이션은 대부분 인프라 및 데이터 서비스에 대한 종속성이 있으며, Azure에도 상주합니다. Azure로 마이그레이션된 내부 애플리케이션은 Tailwind Traders 사용자가 계속 액세스할 수 있어야 합니다. Azure로 마이그레이션된 내부 애플리케이션은 외부 고객이 계속 액세스할 수 있어야 합니다. 

초기 네트워킹 설계를 통합하기 위해 Tailwind Traders Enterprise IT 팀은 Azure로 마이그레이션해야 하는 가장 일반적인 워크로드 범주를 나타내는 두 가지 주요 애플리케이션을 선택했습니다.  

### <a name="design---product-catalog-enterprise-application"></a>설계 - 제품 카탈로그 엔터프라이즈 애플리케이션

![제품 카탈로그 아키텍처](media/catalog.png)

- SQL Server Always On 가용성 그룹 데이터베이스에 호스트되는 제품 카탈로그에 대한 액세스를 제공하는 인터넷 연결 Windows 기반의 2계층 .NET Core 기반 웹앱입니다. 이 애플리케이션은 99.99%의 가용성 SLA, 10분 RPO 및 2시간 RTO를 가진 중요 업무용으로 분류됩니다. 

-   비즈니스 잠재 고객은 인터넷 연결 앱에 액세스할 때 최적의 고객 환경의 중요성을 강조하므로, 웹 페이지를 로드하고 정적 콘텐츠를 다운로드하는 데 걸리는 시간이 최소화되는 것이 중요합니다. 마찬가지로, 웹앱 구성 요소 및 해당 종속성을 호스트하는 개별 서버의 실패는 고객이 인식하는 웹앱 가용성에 무시할 수 있는 영향을 미칠 수 있습니다. 지역 오류로 인해 기존 웹 세션이 일부 중단될 수 있다는 것을 이해하지만, 재해 복구 사이트로의 장애 조치(failover)는 자동이어야 합니다.

- Azure PaaS 서비스에서 제공하는 이점을 활용하기 위해 Enterprise IT 팀은 Azure SQL Database를 사용하여 제품 카탈로그 엔터프라이즈 애플리케이션의 데이터베이스를 구현하기로 결정했습니다. 

- Tailwind Traders 정보 보안 및 위험 팀은 동일한 애플리케이션의 일부인 Azure VM과 PaaS 서비스 간의 모든 통신이 PaaS 서비스의 퍼블릭 엔드포인트를 통하지 않고 Azure 백본을 통해 이동해야 합니다. 

## <a name="tasks---product-catalog-enterprise-application"></a>작업 - 제품 카탈로그 엔터프라이즈 애플리케이션

1. 제품 카탈로그에 대한 2계층 네트워크 솔루션을 설계합니다. 적절한 경우 설계에는 Azure Front Door, WAF, Azure Firewall 및 Azure Load Balancer가 포함될 수 있습니다. 네트워킹 구성 요소를 가상 네트워크로 그룹화해야 하며 네트워크 보안 그룹을 고려해야 합니다. 설계의 각 구성 요소를 선택한 이유를 설명할 준비를 합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?

