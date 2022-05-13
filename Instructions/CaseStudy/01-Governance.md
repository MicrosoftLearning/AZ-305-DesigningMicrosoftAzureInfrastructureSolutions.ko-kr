---
casestudy:
  title: 거버넌스 솔루션 설계
  module: Governance solutions
ms.openlocfilehash: ebf3ce58cc75900f97cdc80a24caeac142fabf9d
ms.sourcegitcommit: 2821f20a573854d6de4599a4edf7cb1bc0fe0ce1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144556375"
---
# <a name="design-a-governance-solution"></a>거버넌스 솔루션 설계

## <a name="requirements"></a>요구 사항

Tailwind Traders는 거버넌스 솔루션에 대한 몇 가지 중요한 변경을 계획하고 있습니다. 권장 사항 및 질문에 대한 지원을 요청했습니다. 특정 요구 사항은 다음과 같습니다.

* **비용 및 회계**. Tailwind Traders에는 의류 및 스포츠 용품을 취급하는 두 개의 주요 사업부가 있습니다. 각 사업부는 세 개의 부서, 제품 개발, 마케팅 및 판매 부서로 구성됩니다. 각 사업부 및 하위 단위는 Azure 지출을 추적해야 합니다. 동시에 Enterprise IT 팀은 회사 차원의 Azure 비용 보고를 제공해야 합니다.

* **새 개발 프로젝트**. 회사는 고객 피드백을 위한 새로운 개발 프로젝트를 가지고 있습니다. CFO는 프로젝트와 관련된 모든 비용을 캡처하려고 합니다. 테스트 단계의 경우 워크로드는 더 저렴한 가상 머신에서 호스트되어야 합니다. 가상 머신에는 프로젝트의 일부임을 나타내는 이름이 지정되어야 합니다. 리소스 일관성 규칙을 준수하지 않는 인스턴스는 자동으로 식별되어야 합니다.

## <a name="tasks"></a>작업

1. **비용 및 회계** 

    * Tailwind Traders에서 구독 및 관리 그룹을 구성할 수 있는 다양한 방법은 무엇인가요? 요구 사항을 충족하는 것이 가장 좋은 것은 무엇인가요? 

    * 두 가지 대체 계층 구조를 설계하고 의사결정 프로세스를 설명합니다.

2. **새 개발 프로젝트** 

    * Tailwind Traders에서 새 개발 프로젝트에 대한 비용을 추적할 수 있는 다양한 방법은 무엇인가요?

    * 가상 머신 크기 조정 및 명명에 대한 요구 사항을 준수하려면 어떻게 해야 하나요? 

    * 요구 사항을 충족하는 두 가지 이상의 방법을 제안합니다. 최종 결정을 설명합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?

