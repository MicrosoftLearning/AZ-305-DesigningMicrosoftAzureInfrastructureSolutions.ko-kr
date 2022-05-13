---
casestudy:
  title: 관계형 스토리지 솔루션 설계
  module: Relational storage solutions
ms.openlocfilehash: 1e616b82df26e492ee943313758952f2ba7e68a6
ms.sourcegitcommit: 2821f20a573854d6de4599a4edf7cb1bc0fe0ce1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2022
ms.locfileid: "144556372"
---
# <a name="design-relational-storage-case-study"></a>관계형 스토리지 설계 사례 연구

## <a name="requirements"></a>요구 사항

Tailwind Traders는 웹 사이트 프런트 엔드도 Azure로 이동되고 있기 때문에, 기존 공개 웹 사이트 데이터베이스를 Azure로 이동할 것을 기대합니다.  웹 사이트 프런트 엔드는 처음에는 중복성을 위해 2개 지역에만 배포됩니다.  그러나 트래픽이 증가함에 따라 웹 사이트가 전세계 다른 지역으로 복제될 것으로 예상됩니다. 마이그레이션해야 하는 데이터베이스에는 제품 카탈로그 및 모든 온라인 주문이 포함됩니다.  현재 데이터베이스는 온-프레미스의 단일 Microsoft SQL Server Always On 가용성 그룹에서 실행됩니다.

Tailwind Traders의 주요 관심사:

-   **고가용성**.  Tailwind Traders의 주요 관심사는 이 데이터베이스가 비즈니스에 중요하기 때문에 가용성이 높다는 것입니다.  가동 중단 시 판매 손실이 초래되거나 고객 신뢰도가 떨어질 수 있습니다.

-   **웹 사이트 성능.**  주문 성능은 일반적으로 만족스럽지만 많은 항목이 나열된 페이지를 찾아보거나 검색하는 성능은 “느린” 것으로 보고됩니다.

-   **보안.**  Tailwind Traders는 노출되는 데이터베이스에 저장된 개인 또는 재무 정보에 대해 매우 걱정하고 있습니다.  보안 팀은 적절한 보안 조치를 구현하는 것 외에도 가능한 경우 업계 표준 모범 사례가 구현되는지 확인해야 합니다.


## <a name="tasks"></a>작업

1.  데이터베이스 솔루션을 설계합니다. 설계에는 권한 부여, 인증, 가격 책정, 성능 및 고가용성이 포함되어야 합니다. 
2.  결정 사항을 다이어그램으로 표시하고 솔루션을 설명합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
