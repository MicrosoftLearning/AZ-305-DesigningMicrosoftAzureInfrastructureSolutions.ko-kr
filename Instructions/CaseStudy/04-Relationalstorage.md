---
casestudy:
  title: 관계형 스토리지 솔루션 설계
  module: Relational storage solutions
---
# <a name="design-relational-storage-case-study"></a>관계형 스토리지 설계 사례 연구

## <a name="requirements"></a>요구 사항

Tailwind Traders is looking to move their existing public website database into Azure, as the website front end is being moved there as well.  The website front end will initially only be deployed in 2 regions for redundancy.  However, it is expected that as traffic increases the website will be replicated to other regions around the world. The database, which you are being asked to migrate, holds the product catalog, and all online orders.  Currently the database runs on a single Microsoft SQL Server Always On availability group on premises.

Tailwind Traders의 주요 관심사:

-   <bpt id="p1">**</bpt>High availability.<ept id="p1">**</ept>  A primary concern for Tailwind Traders is that this database be highly available as it is critical to their business.  Any outages may result in lost sales or customer confidence.

-   <bpt id="p1">**</bpt>Website performance.<ept id="p1">**</ept>  While the performance of placing orders is normally satisfactory, browsing or searching pages with many items listed is reported as being “sluggish.”

-   <bpt id="p1">**</bpt>Security.<ept id="p1">**</ept>  Tailwind Traders is very concerned about personal or financial information stored in the database being exposed.  In addition to implementing proper security measures, the security team needs to verify that industry standard best practices are implemented, when possible.


## <a name="tasks"></a>작업

1.  Tailwind Traders는 웹 사이트 프런트 엔드도 Azure로 이동되고 있기 때문에, 기존 공개 웹 사이트 데이터베이스를 Azure로 이동할 것을 기대합니다. 
2.  결정 사항을 다이어그램으로 표시하고 솔루션을 설명합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
