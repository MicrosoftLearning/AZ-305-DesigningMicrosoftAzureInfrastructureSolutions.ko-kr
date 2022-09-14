---
casestudy:
  title: 비관계형 스토리지 솔루션 설계
  module: Non-relational storage solutions
---
# <a name="design-non-relational-storage-case-study"></a>비관계형 스토리지 설계 사례 연구

## <a name="requirements"></a>요구 사항

Tailwind Traders wants to reduce storage costs by reducing duplicate content and, whenever applicable, migrating it to the cloud. They would like a solution that centralizes maintenance while still providing world-wide access for customers who browse media files and marketing literature. Additionally, they would like to address the storage of company data files. 

![비관계형 스토리지 아키텍처](media/Nonrelational%20storage.png)

 

* <bpt id="p1">**</bpt>Media files<ept id="p1">**</ept>. Media files include product photos and feature videos that are displayed on the company’s public website, which is developed and maintained in house. When a customer browses to an item, the corresponding media files are displayed. The media files are in different formats, but JPEG and MP4 are the most common. 

* <bpt id="p1">**</bpt>Marketing literature<ept id="p1">**</ept>. The marketing literature includes customer stories, sales flyers, sizing charts, and eco-friendly manufacturing information. Internal marketing users access the literature via a mapped drive on their Windows workstations. Customers access the literature directly from the company’s public website.

* <bpt id="p1">**</bpt>Corporate documents<ept id="p1">**</ept>. These are internal documents for departments such as human resources and finance. These documents are accessed and managed via an internally developed web application. Legal requires that various documents be retained for a specific period of time. Occasionally documents will need to be maintained longer when legal or HR issues are being investigated. Most corporate documents older than one year are only kept for compliance reasons and are seldom accessed.

* Tailwind Traders는 중복 콘텐츠를 줄이고 가능할 때마다 클라우드로 마이그레이션하여 스토리지 비용을 줄이려고 합니다. 

* 그들은 미디어 파일 및 마케팅 자료를 검색하는 고객에게 전세계적인 액세스를 제공하면서 유지 관리를 중앙 집중화하는 솔루션을 원합니다. 

## <a name="tasks"></a>작업

1. Tailwind Traders에 대한 스토리지 솔루션을 설계합니다.  

      * 어떤 유형의 데이터를 나타냅니까?  

      * 설계에서 고려할 요소는 무엇일까요?

      * BLOB 액세스 계층을 사용하시겠습니까?

      * 변경할 수 없는 스토리지를 사용하시겠습니까?

      * 콘텐츠에 안전하게 액세스하려면 어떻게 하나요?

2.  또한 회사 데이터 파일의 스토리지를 해결하려고 합니다. 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?
