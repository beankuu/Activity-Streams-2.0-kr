[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 1. [서문 (Introduction)](ActivityStreams2.0Contents.md#목차-table-of-contents)

In the most basic sense, an "Activity" is a semantic description of an action. It is the goal of this specification to provide a JSON-based syntax that is sufficient to express metadata about activities in a rich, human-friendly but machine-processable and extensible manner. This can include constructing natural-language descriptions or visual representations about the activity, associating actionable information with various types of objects, communicating or recording activity logs, or delegation of potential actions to other applications.

가장 기본적인 의미에서의 "액티비티(Activity)"는 행동에 대한 의미론적인 설명입니다. 본 사양의 목표는 액티비티에 관한 메타데이터를 풍부하고 인간 친화적이지만 기계 처리가 가능하고 확장이 가능한 형식으로 표현하기에 충분한 JSON 기반 구문을 제공하는 것입니다. 여기에는 액티비티에 대한 자연어 설명 또는 시각적 표현 구성, 다양한 유형의 개체와 실행 가능한 정보 연결, 통신 또는 작업 로그 기록, 다른 어플리케이션에 대한 잠재적인 작업 위임 등이 포함됩니다.

The key words "*MUST*", "*MUST NOT*", "*REQUIRED*", "*SHALL*", "*SHALL NOT*", " *SHOULD*", "*SHOULD NOT*", "*RECOMMENDED*", "*MAY*", and "*OPTIONAL*" in this document are to be interpreted as described in [[RFC2119](ActivityVocabularyChapterF.md#rfc2119)].

이 문서에 있는 "*반드시 (MUST)*", "*절대 하지 말아야 (MUST NOT)*", "*요구한다 (REQUIRED)*", "*할 것이다 (SHALL)*", "*해서는 안될 것이다 (SHALL NOT)*", "*해야 한다 (SHOULD)*", "*해서는 안된다 (SHOULD NOT)*", "*권장한다 (RECOMMENDED)*", "*할 수도 있다 (MAY)*", 그리고 "*선택적으로 (OPTIONAL)*" 의 키워드들의 해석은  [[RFC2119](ActivityVocabularyChapterF.md#rfc2119)] 를 따릅니다.

### 1.1 [다른 소셜 표준과의 관계 (Relationship to Other Social Standards)](#1-서문-introduction)

_This section is non-normative._

_이 항목은 비표준입니다._

Activity Streams 2.0 is suitable as a social data syntax. It forms part of the [[SWP](ActivityStreams2.0ChapterF.md#swp)] suite of related standards.

Activity Streams 2.0은 소셜 데이터 구문으로 사용하기에 적합합니다. 이 표준은 [[SWP](ActivityStreams2.0ChapterF.md#swp)] 관련 표준 제품군의 일부를 구성합니다.

### 1.2 [JSON Activity Streams 1.0과의 관계 (Relationship to JSON Activity Streams 1.0)](#1-서문-introduction)

_This section is non-normative._

_이 항목은 비표준입니다._

The JSON Activity Streams 1.0 [[AS1](ActivityStreams2.0ChapterF.md#as1)] specification was published in May of 2011 and provided a baseline extensible syntax for the expression of completed activities. This specification builds upon that initial foundation by incorporating lessons learned through extensive implementation, community feedback and related ongoing work from a variety of other communities.

JSON Activity Streams 1.0 [[AS1](ActivityStreams2.0ChapterF.md#as1)] 규격은 2011년 5월에 발표되었으며, 완성된 액티비티의 표현에 대해 확장 가능한 구문의 기반을 제공했습니다. 이 사양은 초기 사양를 기반으로 광범위한 구현, 커뮤니티 피드백 및 기타 다양한 커뮤니티에서 진행 중인 관련 작업을 통해 얻은 교훈을 통합함으로써 만들어졌습니다.

Some of the issues that specifically motivated the evolution of Activity Streams 2.0 from Activity Streams 1.0 include:

Activity Streams 1.0에서 Activity Streams 2.0로 발전시키는 동기를 부여한 몇 가지의 문제점들은 다음과 같았습니다:

- Multi-lingual representation of activities
- Unification of "verb" and "objectType" to "type"
- Removal of activity types and object types that weren't core to social use cases
- Introduction of the Link type for richly-described links
- Incorporation of audience targeting into the core spec
- The generalized "Undo" activity type, so all activities can be undone
- Consistent collection and paging representation
- Formalizing the namespace of the base vocabulary of object types and activity types
- Extensibility framework for other types and properties
- Compatibility with JSON-LD

[//Comment]: # "BLANK"

- 액티비티의 다국어 표현
- "verb"와 "objectType"을 "type"으로 통일
- 소셜 유즈케이스의 핵심이 아닌 액티비티 타입 및 객체 타입 제거
- 상세 설명 링크에 대한 Link 타입 도입
- 핵심 사양에 청중 타게팅 포함
- 모든 액티비티를 취소할수 있기 위해 일반화된 "Undo" 액티비티 타입
- 일관된 컬렉션 및 페이징 표현
- 객체 타입 및 액티비티 타입의 기본 어휘 네임스페이스 공식화
- 다른 타입 및 속성에 대한 확장성 프레임워크
- JSON-LD와의 호환성

The terms `displayName`, `verb`, `title` and `objectType` should be treated as reserved terms that *SHOULD NOT* be used within Activity Streams 2.0 documents. When encountered in an Activity Streams 2.0 document, they SHOULD be processed in accordance to the guidelines listed in [B. Deprecated Activity Streams 1.0 Syntax](https://www.w3.org/TR/activitystreams-core/#activitystreams-1.0a)

`displayName`, `verb`, `title` 그리고 `objectType` 용어는 Activity Streams 2.0 문서에서 사용 *하지 않는* 예약된 용어로 간주해야 합니다. 이들이 Activity Streams 2.0 문서에 있는 경우, [B. 사양된 Activity Streams 1.0 문법](ActivityStreams2.0ChapterB.md) 에 나열된 지침에 따라 처리해야 합니다.

[맨 위로](#1-서문-introduction)
