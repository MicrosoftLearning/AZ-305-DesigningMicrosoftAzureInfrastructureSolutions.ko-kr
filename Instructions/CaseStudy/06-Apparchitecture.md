---
casestudy:
  title: 앱 아키텍처 솔루션 설계
  module: App architecture solutions
---
# <a name="design-an-app-architecture-solution"></a>앱 아키텍처 솔루션 설계

## <a name="requirements"></a>요구 사항

Tailwind Traders is looking to update their website to include customer supplied product images in addition to the already existing photos provided by marketing. They believe that having more photos of products in use will give potential customers a better feel for how past customers loved their products after purchasing them. They do have some requirements as outlined below:

* Uploaded images will need to be scanned before getting posted on the website. Legal and Marketing are both requesting that after initial upload, the images be checked for any issues that reflect poorly upon the company or could cause legal issues. An in-house API has already been developed and deployed that can perform the necessary scanning. 

* Based on existing patterns, Tailwind Traders expects the image uploads to happen very unevenly throughout the day. Certain periods may experience more uploads than the scanning software can handle, while other periods may experience very few or no uploads.

* 업로드된 이미지가 시스템에서 스캔되고 승인되었으면, Tailwind Traders는 고객에게 이미지 공유를 감사해하는 메일을 보낼 것을 원합니다.

* Cost and management of the solution is a concern, especially since Tailwind Traders isn’t sure how popular this feature will be initially. Minimize costs and leverage serverless solutions where possible.

 

![앱 아키텍처](media/Apparchitecture.png)

 

## <a name="task"></a>Task

회사 웹 사이트에 고객 이미지를 추가하기 위한 아키텍처를 설계합니다.  

* 이미지를 어디에 저장해야 하나요?

* 업로드가 스캔을 능가하는 경우에도 모든 이미지가 스캔되도록 하려면 어떻게 해야 하나요?

* 이미지가 승인되고 카탈로그 데이터베이스가 업데이트되면 고객에게 어떻게 알리나요? 

고품질의 안정적이고 효율적인 클라우드 아키텍처를 생성하기 위해 Well Architected Framework 핵심 요소를 통합하려면 어떻게 해야 할까요?

 
