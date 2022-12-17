---
title: 온라인 호스팅 지침
permalink: index.html
layout: home
---

# <a name="content-directory"></a>콘텐츠 디렉터리

각 사례 연구에 대한 하이퍼링크는 아래와 같습니다.

## <a name="case-studies"></a>사례 연구

{% assign casestudy = site.pages | where_exp:"page", "page.url contains '/Instructions/CaseStudy'" %}
| 모듈 | 사례 연구 |
| --- | --- | 
{% for activity in casestudy  %}| {{ activity.casestudy.module }} | [{{ activity.casestudy.title }}{% if activity.casestudy.type %} - {{ activity.casestudy.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
