[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 9. [규정 (Conformance)](ActivityStreams2.0Contents.md#목차-table-of-contents)

All diagrams, examples, and notes in this specification are non-normative, as are all sections explicitly marked non-normative. Everything else in this specification is normative.

비 표준으로 표시된 항목들과 마찬가지로, 본 사양의 모든 도표, 예시, 노트들은 비 표준입니다. 그 외의 모든 것들은 표준입니다.

[//TODO]: # "Conformance가 규정 / 준수로 나뉘어 번역되고 있습니다. 이는 차후에 재 검토를 반드시 해야할것 같습니다."

### 9.1 [문서 (Documents)](#9-규정-conformance)

Conforming documents are those that comply with all the conformance criteria for documents. For readability, some of these conformance requirements are phrased as conformance requirements on publishers; such requirements are implicitly requirements on documents: by definition, all documents are assumed to have a publisher.

규정 문서는 모든 기준을 준수하는 문서입니다. 가독성을 위해 이러한 준수 조건중 일부는 출판자가 준수할 사항으로 표현됩니다; 이러한 요구사항들은 문서에 대한 암시적인 요구사항입니다: 정의에 따르면, 모든 문서에는 출판자가 있다고 가정됩니다.

Conforming documents must not include deprecated or obsolete syntax from Activity Streams 1.0. Conforming documents must include properties and types from the Activity Vocabulary. Conforming documents that use other vocabularies must also include equivalent Activity Vocabulary properties and types as illustrated in Section C. Conforming documents must not use features of JSON-LD or other serialization features disallowed in this specification, as in Section 2. Conforming documents that include types or properties beyond those defined in the Activity Streams 2.0 Vocabulary must use the extensibility features defined in section 5.

규정 문서는 Activity Streams 1.0에서 사용되지 않거나 더 이상 사용되지 않는 구문을 절대 포함해서는 안됩니다. 규정 문서에서는 액티비티-어휘의 속성 및 타입들을 반드시 포함해야 합니다. 다른 어휘를 사용하는 규정 문서에서는 섹션 C에 나와있는 것과 같은 액티비티-어휘 속성 및 타입들도 반드시 포함해야 합니다. 규정 문서는 섹션 2와 같이 이 규격에서 허용되지 않는 JSON-LD 기능 또는 기타 직렬화 기능을 절대 사용해서는 안됩니다. Activity Streams 2.0 에 정의된 것 이상의 타입 또는 속성을 포함하는 규정 문서는 섹션 5에 정의된 확장 기능을 반드시 사용해야 합니다.

A non-exhaustive list of examples of documents includes:

문서 예시 목록에는 다음이 포함됩니다:

- A document representing an actor
- A document representing an object
- A document representing an activity
- A document representing a collection of the activities done by an actor
- A document representing a collection of the activities done to an object
- A document representing a collection of the activities addressed to an actor or object

[//Comment]: # "BLANK"

- 액터를 나타내는 문서
- 객체를 나타내는 문서
- 액티비티를 나타내는 문서
- 액터가 수행한 액티비티의 컬렉션을 나타내는 문서
- 객체에 수행된 액티비티의 컬렉션을 나타내는 문서
- 액터 또는 객체로 지정된 액티비티들의 컬렉션을 나타내는 문서

### 9.2 [구현 (Implementations)](#9-규정-conformance)

Conforming implementations are software that publish, store, analyze, consume or otherwise process conforming documents. The two main kinds of implementations are publishers and consumers.

규정을 준수하는 구현은 규정 문서를 게시, 저장, 분석, 소비 또는 처리하는 소프트웨어입니다. 구현의 두 가지 주요 유형은 출판자와 소비자입니다.

#### 9.2.1 [출판자 (Publishers)](#92-구현-implementations)

Conforming publishers are implementations that create and publish conforming documents. Conforming publishers must make conforming documents available according to the serialization requirements of section 2. Conforming publishers must consider privacy as described in section 6. Conforming publishers must consider security as described in section 7.

준수 출판자는 규정 문서를 작성하고 게시하는 경우의 구현입니다. 준수하는 출판자는 섹션 2의 직렬화 요구 사항에 따라 반드시 적합한 문서를 제공해야 합니다. 준수 게시자는 섹션 6에 설명된 대로 반드시 개인 정보를 고려해야 합니다. 준수 게시자는 섹션 7에 설명된 대로 반드시 보안을 고려해야 합니다.

A non-exhaustive list of example publishers includes:

출판자 예시 목록에는 다음이 포함됩니다:

- A social network
- A personal web site
- A document publishing system
- A bridge from a non-conforming social network
- A document converter from similar document types such as RSS or Atom

[//Comment]: # "BLANK"

- 소셜 네트워크
- 개인 웹사이트
- 문서 출판 시스템
- 부적합한 소셜 네트워크에서의 브릿지
- RSS 또는 Atom과 같은 유사한 문서 유형의 문서 변환기

#### 9.2.2 [소비자 (Consumers)](#92-구현-implementations)

Conforming consumers are implementations that read and analyze conforming documents. Conforming consumers must tolerate deprecated or obsolete properties or types from Activity Streams 1.0. Conforming consumers must ignore properties or types that are not applicable to their application domain.

준수 소비자는 준수 문서를 읽고 분석하는 구현체입니다. 준수 소비자는 Activity Streams 1.0의 더이상 사용되지 않거나 더이상 사용되지 않는 속성 또는 타입을 감수해야 합니다. 준수 소비자는 애플리케이션 도메인에 해당되지 않는 속성이나 유형을 무시해야 합니다.

Conforming consumers may re-publish conforming documents in other other data formats. Conforming consumers may present conforming documents to a user on screen, in print, in audio format, or using other presentation mechanisms. Conforming consumers must faithfully translate the information represented in conforming documents into these other formats or media. Conforming consumers that re-publish conforming documents must consider privacy as described in section 6 and security as described in section 7.

준수 소비자는 다른 데이터 형식으로 규정 문서를 다시 게시할수 있습니다. 준수 소비자는 화면, 인쇄, 오디오 형식 또는 기타 프리젠테이션 메커니즘을 사용하여 사용자에게 적합한 문서를 제공 할 수도 있습니다. 준수 소비자는 반드시 규정 문서에 표시된 정보를 이러한 다른 형식이나 매체로 충실히 번역해야 합니다. 규정 문서를 다시 게시하는 소비자는 반드시 섹션 6에 설명된 대로 개인 정보와 섹션 7에 설명된 보안을 고려해야 합니다.

A non-exhaustive list of example consumers includes:

소비자 예시 목록에는 다음이 포함됩니다:

- 소셜 네트워크
- 검색 엔진
- 피드 리더
- 문서 유효성 검사기
- 피드 집계기
- 통계 분석기

[맨 위로](#9-규정-conformance)
