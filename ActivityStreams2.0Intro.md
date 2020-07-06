[목차로 돌아가기](ActivityStreams2.0Contents.md)

# [액티비티스트림(Activity Streams) 2.0](https://www.w3.org/TR/activitystreams-core/)

<abbr title="World Wide Web Consortium">W3C</abbr> Recommendation 23 May 2017

2017년 5월 23일 <abbr title="World Wide Web Consortium">W3C</abbr>권고안

**This version:**

**현재 버전**
- https://www.w3.org/TR/2017/REC-activitystreams-core-20170523/

**Latest published version:**

**최신 게시 버전**
- https://www.w3.org/TR/activitystreams-core/

**Latest editor's draft:**

**최신 편집자 초안**
- http://w3c.github.io/activitystreams/core/

**Test suite:**

**테스트 모음**
- https://github.com/w3c/activitystreams/tree/master/test

**Implementation report:**

**구현 보고서**
- https://github.com/w3c/activitystreams/tree/master/implementation-reports

**Previous version:**

**이전 버전**
- https://www.w3.org/TR/2017/PR-activitystreams-core-20170413/

**Editors:**

**편집자:**
- [James M Snell](http://jasnell.me/), IBM 
- [Evan Prodromou](https://fuzzy.ai/about), Fuzzy.ai 

**Repository:**
- [Github](https://github.com/w3c/activitystreams) 
- [Issues](https://github.com/w3c/activitystreams/issues) 
- [Commits](https://github.com/w3c/activitystreams/commits/master) 

**저장소**
- [Github](https://github.com/w3c/activitystreams) 
- [이슈들](https://github.com/w3c/activitystreams/issues) 
- [커밋들](https://github.com/w3c/activitystreams/commits/master) 

**Test:**
- [Validator](https://as2.rocks/) 

**테스트**
- [검증기](https://as2.rocks/)

Please check the [**errata**](https://github.com/w3c/activitystreams/blob/master/ERRATA.md) for any errors or issues reported since publication.

이 게시물 이후 보고된 오류나 이슈에 대해서는 [**정오표**](https://github.com/w3c/activitystreams/blob/master/ERRATA.md) 를 확인해 주시길 바랍니다.

The English version of this specification is the only normative version. Non-normative [translations](https://www.w3.org/2003/03/Translations/byTechnology?technology=https://www.w3.org/TR/activitystreams-vocabulary/) may also be available.

이 표준은 영어 버전만이 유일한 표준 버전입니다. 비-표준적인 [번역본](https://www.w3.org/2003/03/Translations/byTechnology?technology=https://www.w3.org/TR/activitystreams-vocabulary/)들도 제공될 수도 있습니다.

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [liability](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [trademark](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks) and [permissive document license](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) rules apply.

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="매사추세츠 공과대학교">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [법적 책임](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [상표](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks)와 [문서 허용 라이센스](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) 규칙이 적용됩니다.

-----

## 요약 (Abstract)

This specification details a model for representing potential and completed activities using the JSON format. It is intended to be used with vocabularies that detail the structure of activities, and define specific types of activities.

이 사양은 JSON형식을 사용하여 잠재적이고 완료된 액티비티들을 표현하는 모델을 구체적으로 설명하고 있습니다. 이는 액티비티의 구조를 상세히 기술하고 특정한 액티비티들의 유형을 정의하는 어휘와 함께 사용하기 위하도록 고안되었습니다.

### 글쓴이의 말 (Author's Note)

_This section is non-normative._

_이 항목은 비표준입니다._

This draft is heavily influenced by the JSON Activity Streams 1.0 specification originally co-authored by Martin Atkins, Will Norris, Chris Messina, Monica Wilkinson, Rob Dolin and James Snell. The author is very thankful for their significant contributions and gladly stands on their shoulders. Some portions of the original text of Activity Streams 1.0 are used in this document.

이 초안은 Martin Atkins, Will Norris, Chris Messina, Monica Wilkinson, Rob Dolin 과 James Snell이 공동 작성한 JSON Activity Streams 1.0 문서의 영향을 많이 받았습니다. 저자는 그들의 중대한 기여에 대해 매우 감사하며 그들의 노고를 잊지 않을겁니다. Activity Streams 1.0 원문의 일부는 이 문서에서 그대로 사용됩니다.

## 이 문서의 상태 (Status of This Document)

_This section describes the status of this document at the time of its publication. Other documents may supersede this document. A list of current <abbr title="World Wide Web Consortium">W3C</abbr> publications and the latest revision of this technical report can be found in the [<abbr title="World Wide Web Consortium">W3C</abbr> technical reports index](https://www.w3.org/TR/) at https://www.w3.org/TR/._

_이 문단에서는 현 문서의 발행 당시의 상태에 대하여 기술합니다. 다른 문서가 이 문서를 대체 할 수 있습니다. 현재 <abbr title="World Wide Web Consortium">W3C</abbr> 출판물 목록 및 이 기술보고서의 최신 개정판은 https://www.w3.org/TR/ 에 있는 [<abbr title="World Wide Web Consortium">W3C</abbr> 기술보고서 색인](https://www.w3.org/TR/)에서 찾아볼 수 있습니다._

This document was published by the [Social Web Working Group](https://www.w3.org/Social/WG) as a Recommendation. Comments regarding this document are welcome. Please send them to [public-socialweb@w3.org](public-socialweb@w3.org) ([subscribe](public-socialweb-request@w3.org), [archives](https://lists.w3.org/Archives/Public/public-socialweb/)).

이 문서는 [소셜 웹 워킹 그룹(Social Web Working Group)](https://www.w3.org/Social/WG)에 의하여 작성된 권고안입니다. 이 문서에 관한 의견은 언제나 환영합니다. 의견이 있을시 public-socialweb@w3.org ([구독](public-socialweb-request@w3.org), [기록들](https://lists.w3.org/Archives/Public/public-socialweb/))로 보내주시길 바랍니다.

Please see the Working Group's [implementation report](https://github.com/w3c/activitystreams/tree/master/implementation-reports).

작업 그룹의 [구현 레포트](https://github.com/w3c/activitystreams/tree/master/implementation-reports)를 확인해 주시길 바랍니다.

This document has been reviewed by <abbr title="World Wide Web Consortium">W3C</abbr> Members, by software developers, and by other <abbr title="World Wide Web Consortium">W3C</abbr> groups and interested parties, and is endorsed by the Director as a <abbr title="World Wide Web Consortium">W3C</abbr> Recommendation. It is a stable document and may be used as reference material or cited from another document. <abbr title="World Wide Web Consortium">W3C</abbr>'s role in making the Recommendation is to draw attention to the specification and to promote its widespread deployment. This enhances the functionality and interoperability of the Web.

이 문서는 <abbr title="World Wide Web Consortium">W3C</abbr> 회원, 소프트웨어 개발자 및 기타 W3C 그룹과 이해 관계자들에게 검토되었으며, 위원장이 <abbr title="World Wide Web Consortium">W3C</abbr> 권고안으로 발표하였습니다. 이 문서는 안정적이며, 참고자료로 사용되거나 다른 문서에서 인용될수 있습니다. <abbr title="World Wide Web Consortium">W3C</abbr>가 권고안을 만드는 것은 표준사양에 대하여 주의를 환기시키고, 보다 넓은 범위에서 그 사용을 촉진시키기 위함입니다. 이는 웹의 기능성과 보편성을 향상시킬 수 있습니다.

This document was produced by a group operating under the [5 February 2004 <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy-20040205/). <abbr title="World Wide Web Consortium">W3C</abbr> maintains a [public list of any patent disclosures](https://www.w3.org/2004/01/pp-impl/72531/status) made in connection with the deliverables of the group; that page also includes instructions for disclosing a patent. An individual who has actual knowledge of a patent which the individual believes contains [Essential Claim(s)](https://www.w3.org/Consortium/Patent-Policy-20040205/#def-essential) must disclose the information in accordance with [section 6 of the <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy-20040205/#sec-Disclosure).

이 문서는 [2004년 02월 05일 <abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책](https://www.w3.org/Consortium/Patent-Policy/)에 따라 운영되는 그룹이 작성하였습니다. <abbr title="World Wide Web Consortium">W3C</abbr>는 그룹의 성과물에 관한 [모든 공개 특허 공개 목록](https://www.w3.org/2004/01/pp-impl/72531/status)을 관리합니다. 이곳에서는 특허 공개에 대한 지시사항도 포함됩니다. [필수 주장(들)](https://www.w3.org/Consortium/Patent-Policy-20040205/#def-essential)을 포함한다고 생각되는 특허에 대하여 실제 지식을 보유한 개인은 [<abbr title="World Wide Web Consortium">W3C</abbr> 특허 정책의 섹션 6](https://www.w3.org/Consortium/Patent-Policy-20040205/#sec-Disclosure)에 의하여 정보를 공개하여야 합니다.

This document is governed by the [1 March 2017 <abbr title="World Wide Web Consortium">W3C</abbr> Process Document](https://www.w3.org/2017/Process-20170301/).

이 문서는 [2017년 3월 1일 <abbr title="World Wide Web Consortium">W3C</abbr> 프로세스 문서](https://www.w3.org/2017/Process-20170301/)를 적용받습니다.

[맨 위로](#액티비티스트림activity-streams-2.0)