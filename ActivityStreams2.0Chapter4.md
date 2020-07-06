[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 4. [모델 (Model)](ActivityStreams2.0Contents.md#목차-table-of-contents)

The [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) normatively defines the core object types and properties for Activity Streams 2.0.

[Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/)는 Activity Streams 2.0의 핵심 객체 타입들 및 속성을 규범적으로 정의합니다.

The object types defined by the vocabulary are segmented into a set of eight core types and an extended set of Activity and Object types common to many social Web applications. The core types include:

어휘에 의해 정의된 객체 타입은 8개의 핵심 타입 집합과 많은 소셜 웹 어플리케이션에 공통되는 확장된 액티비티 및 객체 타입 집합으로 구분됩니다. 핵심 타입들은 다음과 같습니다:

- [Object](#41-객체-object),
- [Link](#42-링크-link),
- [Activity](#44-액티비티-activity),
- [IntransitiveActivity](#45-비-과도적-액티비티-intransitiveactivity),
- [Collection](#46-컬렉션-collection),
- [`OrderedCollection`](#orderedcollection),
- [`CollectionPage`](#collectionpage), 그리고
- [`OrderedCollectionPage`](#orderedcollectionpage) 입니다.

Every JSON object in an Activity Streams 2.0 document is either an [Object](#41-객체-object) or a [Link](#42-링크-link). All other types defined in the Activity Vocabulary, as well as all extension types, are derived from these two base types.

Activity Streams 2.0 문서의 모든 JSON 객체는 [Object](#41-객체-object) 거나 [Link](#42-링크-link) 입니다. Activity 어휘에 정의된 다른 모든 타입들과 모든 확장 타입들은 일거한 두 가지 기본 타입에서 파생됩니다.

A JSON object in the Activity Streams 2.0 document is a [Link](#42-링크-link) if either: (a) the object contains a `type` property whose value includes "`Link`" or (b) any of the types included in the value of the `type` property are defined as extensions of [Link](#42-링크-link) (see [Mention](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-mention) for instance); otherwise the JSON object is considered an instance or extension of [Object](#41-객체-object).

Activity Streams 2.0 문서의 JSON 객체는 다음 중 아무 조건이나 만족할 경우 [Link](#42-링크-link) 입니다: (a) 객체 값에 "`Link`"가 포함된 `type` 속성이 있거나, (b) `type` 속성 값에 포함된 모든 타입들이 [Link](#42-링크-link)의 확장으로 정의되었을 경우 ([Mention](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-mention) 을 참조하시길 바랍니다); 위 사항에 해당하지 않을 경우 JSON 객체는 [Object](#41-객체-object)의 인스턴스나 확장으로 간주됩니다.

### 4.1 [객체 (Object)](#4-모델-model)

The [Object](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-object) is the primary base type for the Activity Streams vocabulary.

[Object](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-object)는 Activity Streams 어휘의 주요 기반 타입입니다.

In addition to having a global identifier (expressed as an absolute IRI using the `id` property) and an "object type" (expressed using the `type` property), all instances of the `Object` type share a common set of properties normatively defined by the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/). These include:

전역 식별자(`id` 속성을 사용하여 절대 IRI로 표시됨)와 "객체 타입"(`type` 속성을 사용하여 표시됨)을 갖는 것 외에도, `Object` 타입의 모든 인스턴스는 [Activity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 의해 규범적으로 정의된 공통 속성 집합을 공유합니다. 여기에는 다음이 포함됩니다:
 [attachment](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-attachment) |
 [attributedTo](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-attributedto) |
 [audience](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-audience) |
 [content](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content) |
 [context](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-context) |
 [contentMap](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content) |
 [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) |
 [nameMap](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) |
 [endTime](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-endtime) |
 [generator](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-generator) |
 [icon](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-icon) |
 [image](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-image-term) |
 [inReplyTo](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-inreplyto) |
 [location](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-location) |
 [preview](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-preview) |
 [published](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-published) |
 [replies](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-replies) |
 [startTime](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-starttime) |
 [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) |
 [summaryMap](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) |
 [tag](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-tag) |
 [updated](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-updated) |
 [url](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-url) |
 [to](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-to) |
 [bto](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-bto) |
 [cc](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-cc) |
 [bcc](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-bcc) |
 [mediaType](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-mediatype) |
 [duration](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-duration)

All properties are optional (including the `id` and `type`).

모든 속성은 선택사항입니다 (`id`와 `type`도 해당함).

<div align="center"><em>
Figure 7 Following is an example Object that uses the `id` and `type` properties to express the global identifier and object type:
</em></div>

<div align="center" id="도표-7-다음은-id와-type-속성을-사용하여-전역-식별자와-객체-타입을-나타내는-객체object의-예시"><em>
도표 7 다음은 `id`와 `type` 속성을 사용하여 전역 식별자와 객체 타입을 나타내는 객체(Object)의 예시:
</em></div>

><div align="center"> Example 7 </div>
>
>```json
>{
>  "name": "My favourite stew recipe",
>}
>```

><div align="center"> 예시 7 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "id": "http://example.org/foo",
>  "type": "Note",
>  "name": "내가 가장 좋아하는 스튜 요리법",
>  "attributedTo": {
>    "id": "http://joe.website.example/",
>    "type": "Person",
>    "name": "Joe Smith"
>  },
>  "published": "2014-08-21T12:34:56Z"
>}
>```

The [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) defines a range of `Object` types that are common to many social Web applications. This specification stops short of defining semantically specific properties for most of these objects. External vocabularies can be used to express additional detail not covered by the Activity Vocabulary.

[Activity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)는 많은 소셜 웹 어플리케이션에게 공통적인 `Object` 타입을 정의합니다. 이 사양은 이러한 대부분의 객체(objects)에 대해 의미론적으로 세부적인 특정 속성들을 정의하지는 않습니다. 외부 어휘를 사용하여 Activity 어휘에서 다루지 않는 추가적인 세부 정보를 표현할 수 있습니다.

Furthermore, while implementations are free to introduce new types of Objects beyond those defined by the Activity Vocabulary, interoperability issues can arise when applications rely too much on extension types that are not recognized by other implementations. Care should be taken to not unduly overlap with or duplicate the existing Object types.

또한, 구현은 Activity 어휘에서 정의한 것과 다른 새로운 객체(Objects) 타입을 자유롭게 도입할 수 있지만, 어플리케이션이 다른 구현에서 인식하지 못하는 확장 타입에 너무 많이 의존할 경우 상호 운용성 문제가 발생할 수 있습니다. 기존의 Object 타입과 과도하게 겹치거나 중복되지 않도록 주의해야 합니다.

When an implementation uses an extension type that overlaps with a core vocabulary type, the implementation *MUST* also specify the core vocabulary type. For instance, some vocabularies (e.g. The Good Relations Vocabulary) define their own types for describing locations. An implementation that wishes, for example, to use a http://purl.org/goodrelations/v1#Location as an object type *MUST* also identify the object as being a [Place](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-place) as illustrated in the following:

구현에서 핵심 어휘 타입과 겹치는 확장 타입을 사용하는 경우, 구현에서는 *반드시* 핵심 어휘 타입도 지정해야 합니다. 예를 들어, 일부 어휘(예: Good Relations 어휘)는 위치를 설명하기 위한 고유한 타입을 정의합니다. 예를 들어, http://purl.org/goodrelations/v1#Location을 객체 타입으로 사용하려는 구현에서는 *반드시* 다음 도표처럼 객체를 [Place](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-place) 로 식별해야 합니다.

<div align="center"><em>
Figure 8 An Object that is both a <code>Place</code> and a <code>gr:Location</code>:
</em></div>

<div align="center" id="도표-8-place이면서-grlocation인-객체"><em>
도표 8 <code>Place</code>이면서 <code>gr:Location</code>인 객체:
</em></div>


><div align="center"> Example 8 </div>
>
>```json
>{
>  "name": "Sally's Restaurant",
>}
>```

><div align="center"> 예시 8 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {
>      "gr": "http://purl.org/goodrelations/v1#"
>    }
>  ],
>  "type": ["Place", "gr:Location"],
>  "name": "Sally의 레스토랑",
>  "longitude": 12.34,
>  "latitude": 56.78,
>  "gr:category": "restaurants/french_restaurants"
>}
>```

Certain properties defined by some External Vocabularies can overlap or duplicate those defined by the Activity Vocabulary. Where such overlap exists, for the sake of consistent interoperability, implementations *MUST* favor the use of properties defined by the Activity Vocabulary.

일부 외부 어휘에 의해 정의된 특정 속성은 Activity 어휘에 의해 정의된 속성과 겹치거나 중복될 수 있습니다. 이러한 중복이 존재하는 경우, 일관된 상호 운용성을 위해 구현은 *반드시* Activity 어휘에 의해 정의된 속성을 선호해야 합니다.

### 4.1.1 [객체 타입의 텍스트 표현 Text representations of Object types](#41-객체-object)

Activity Streams consumers often need a text representation of an Activity Streams object, e.g. for display in a Web browser or console interface.

Activity Streams 소비자는 웹 브라우저 또는 콘솔 인터페이스에 표시하기 위한것 처럼 Activity Streams 객체의 텍스트 표시가 필요한 경우가 많습니다.

The [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) property *SHOULD* be derived from input by the creator or another user.

[name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) 속성은 작성자 또는 다른 사용자의 입력에서 *파생되어야 합니다*.

The [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) property *SHOULD* be used as a fallback text representation, possibly automatically generated by the publisher. If there is no `name` property, the `summary` property *SHOULD NOT* include markup, and *SHOULD* be short enough to be used as a reasonable text representation of the object.

[summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) 속성은 게시자가 자동으로 생성하는 예비 텍스트 표현으로 *사용해야 합니다*. `name` 속성이 없는 경우 `summary` 속성은 마크업을 *포함하지 말아야* 하며 객체의 적절한 텍스트 표현으로 사용할 수 있을 정도로 *짧아야 합니다*.

<div align="center"><em>
Figure 9 A note with a name defined by the author
</em></div>

<div align="center" id="도표-9-저자가-정의한-이름을-가지고-있는-노트"><em>
도표 9 저자가 정의한 이름을 가지고 있는 노트
</em></div>

><div align="center"> Example 9 </div>
>
>```json
>{
>  "name": "Our Weather Is Fine",
>  "content": "I feel that the weather is appropriate to our season and location."
>}
>```

><div align="center"> 예시 9 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Note",
>  "id": "http://example.org/note/123",
>  "name": "저희 날씨는 괜찮아요",
>  "content": "날씨가 저희의 계절과 장소에 적합하다고 생각되어요."
>}
>```

<div align="center"><em>
Figure 10 A note with an automatically-generated summary
</em></div>

<div align="center" id="도표-10-자동으로-생성된-요약본이-있는-노트"><em>
도표 10 자동으로 생성된 요약본이 있는 노트
</em></div>

><div align="center"> Example 10 </div>
>
>```json
>{
>  "summary": "A note by Sally",
>  "content": "Everything is OK here."
>}
>```

><div align="center"> 예시 10 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Note",
>  "id": "http://example.org/note/124",
>  "summary": "Sally의 노트",
>  "content": "여긴 아무 문제 없어요."
>}
>```

The `name` and `summary` *MAY* be absent, *MAY* lack explicit values in the end user's current language, and *MAY* be longer than appropriate for use as a text representation of the Object in the current language context. Consumer implementations *SHOULD* have fallback strategies for text representation of Objects in these cases.

`name`과 `summary` 없을 *수도* 있으며, 최종 사용자의 현재 언어에 명시적 값이 부족할 *수도* 있으며, 현재 언어 컨텍스트에서 객체의 텍스트 표현으로 사용하기에 적절하지 않을 *수도* 있습니다. 소비자의 구현은 이러한 경우의 객체의 텍스트 표현을 위한 대비책이 *있어야 합니다*.

### 4.2 [링크 (Link)](#4-모델-model)

A `Link` describes a qualified, indirect reference to another resource that is closely related to the conceptual model of Links as established in [[RFC5988](https://www.w3.org/TR/activitystreams-core/#bib-RFC5988)]. The properties of the Link object are not the properties of the referenced resource, but are provided as hints for rendering agents to understand how to make use of the resource. For example, `height` and `width` might represent the desired rendered size of a referenced image, rather than the actual pixel dimensions of the referenced image.

`Link`는 [[RFC5988](https://www.w3.org/TR/activitystreams-core/#bib-RFC5988)]에서 설정된 링크(Links)의 개념 모델과 밀접하게 관련된, 다른 리소스에 대한 적격적인 간접 참조를 설명합니다. Link 객체의 속성은 참조된 리소스의 속성은 아니지만, 렌더링 에이전트에게 리소스 사용 방법을 이해시키기 위한 힌트로 제공됩니다. 예를 들어 `height`와 `width`는 참조된 이미지의 실제 픽셀 치수가 아니라 참조된 이미지의 원하는 렌더링 크기를 나타낼 수 있습니다.

The target URI of the Link is expressed using the required [href](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-href) property. In addition, all `Link` instances share the following common set of optional properties as normatively defined by the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/):

Link의 대상 URI는 필요한 [href](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-href) 속성을 사용하여 표시됩니다. 또한 모든 `Link` 인스턴스는 [Activity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 의해 표준으로 정의된 다음과 같은 공통 선택 속성 집합을 공유합니다:
 [id](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-id) |
 [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) |
 [hreflang](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-hreflang) |
 [mediaType](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-mediatype) |
 [rel](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-rel) |
 [height](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-height) |
 [width](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-width)

For example, all [Objects](#41-객체-object) can contain an [image](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-image-term) property whose value describes a graphical representation of the containing object. This property will typically be used to provide the URL to an image (e.g. JPEG, GIF or PNG) resource that can be displayed to the user. Any given object might have multiple such visual representations -- multiple screenshots, for instance, or the same image at different resolutions. In Activity Streams 2.0, there are essentially three ways of describing such references.

예를 들어 모든 [Objects](#41-객체-object)는 포함된 객체의 그래픽 표현을 설명하는 값을 가진 [image](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-image-term) 속성을 포함할 수 있습니다. 이 속성은 일반적으로 사용자에게 표시할 수 있는 이미지(예: JPEG, GIF 또는 PNG) 리소스에 URL을 제공하는 데 사용됩니다. 지정된 객체에는 이러한 여러 시각적 표현(예: 여러 스크린샷 또는 다른 해상도의 동일한 이미지)이 있을 수 있습니다. Activity Streams 2.0 에서는 기본적으로 이러한 참조를 설명하는 세 가지 방법이 있습니다.

<div align="center"><em>
Figure 11 To reference a single image without any additional metadata, a direct association can be expressed as a JSON string containing an absolute IRI.
</em></div>

<div align="center" id="도표-11-추가-메타데이터-없이-단일-이미지를-참조하기-위해-직접-연관을-절대-iri를-포함하는-json-문자열로-표현할수-있다"><em>
도표 11 추가 메타데이터 없이 단일 이미지를 참조하기 위해, 직접 연관을 절대 IRI를 포함하는 JSON 문자열로 표현할수 있다.
</em></div>

><div align="center"> Example 11 </em>
>
>```json
>{
>  "name": "Exampletron 3000",
>}
>```

><div align="center"> 예시 11 </em>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Application",
>  "id": "http://example.org/application/123",
>  "name": "예시제조기 3000",
>  "image": "http://example.org/application/123.png"
>}
>```

<div align="center"><em>
Figure 12 Alternatively, if additional metadata is required (such as the MIME content type of the referenced resource) a <a href="#42-링크-link">Link</a> can be used:
</em></div>

<div align="center" id="도표-12-다르게-추가-메타데이터가-필요한-경우-예-참조된-리소스의-mime-컨텐츠-타입-Link를-사용할수-있다"><em>
도표 12 다르게, 추가 메타데이터가 필요한 경우 (예: 참조된 리소스의 MIME 컨텐츠 타입) <a href="#42-링크-link">Link</a>를 사용할수 있다:
</em></div>

><div align="center"> Example 12 </div>
>
>```json
>{
>  "name": "Exampletron 3000",
>}
>```

><div align="center"> 예시 12 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Application",
>  "id": "http://example.org/application/123",
>  "name": "예시제조기 3000",
>  "image": {
>    "type": "Link",
>    "href": "http://example.org/application/123.png",
>    "mediaType": "image/png"
>  }
>}
>```

Formally, the former example establishes an unqualified direct relationship with the image resource while the latter creates a [qualified, indirect relationship](http://patterns.dataincubator.org/book/qualified-relation.html) that allows additional properties about the relationship to be specified.

정식적으로 보면, 전자의 예는 이미지 리소스와 부적격적인 직접 관계를 만드는 반면, 후자는 해당 관계에 대한 추가 속성을 지정할 수 있는 [적격적인 간접 관계](http://patterns.dataincubator.org/book/qualified-relation.html)를 만듭니다.

[//Comment]: # "Formally -> 정식적 으로 번역하였으나 매끄럽지 않은것 같습니다"

<div align="center"><em>
Figure 13 If more than one value is to be expressed, A JSON Array with a mix of strings and <a href="#42-링크-link">Link</a>s can be used:
</em></div>

<div align="center"><em>
도표 13 둘 이상의 값을 표현하려는 경우, 문자열과 <a href="#42-링크-link">Link</a>가 혼합된 JSON 배열을 사용할수 있다:
</em></div>

><div align="center"> Example 13 </div>
>
>```json
>{
>  "name": "Exampletron 3000",
>}
>```

><div align="center"> 예시 13 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Application",
>  "id": "http://example.org/application/123",
>  "name": "예시제조기 3000",
>  "image": [
>    "http://example.org/application/abc.gif",
>    {
>      "type": "Link",
>      "href": "http://example.org/application/123.png",
>      "mediaType": "image/png"
>    }
>  ]
>}
>```

Individual items contained in such an array are independent of one another and no significance is given to the ordering.

이러한 배열에 포함된 개별 항목들은 서로 독립적이며 순서에 의미를 두지 않습니다.

RFC 5988 defines that all Links have a "link relation" that describes the contextual purpose of the link. Within a [Link](#42-링크-link), the [rel](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-rel) property provides the link relation value. If no `rel` property is specified, the link relation is considered to be unspecified. Any given Link can have multiple link relation values. In the JSON serialization, a single link relation is expressed as a single JSON string. Multiple link relations are expressed as an array of JSON strings.

RFC 5988은 모든 링크가 링크의 상황별 목적을 설명하는 "링크 관계(link relation)"를 가지고 있다고 정의합니다. [Link](#42-링크-link) 내에서 [rel](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-rel) 속성은 링크 관계 값을 제공합니다. `rel` 속성을 지정하지 않으면 링크 관계가 지정되지 않은 것으로 간주됩니다. 어떠한 Link던 상관없이 여러 링크 관계 값을 보유하고 있을 수 있습니다. JSON 직렬화에서 단일 링크 관계는 단일 JSON 문자열로 표현됩니다. 다중 링크 관계는 JSON 문자열의 배열로 표현됩니다.

The scope of the link relation is the object in which the [Link](#42-링크-link) is an immediate child.

링크 관계의 범위는 [Link](#42-링크-link)가 직계 하위 항목인 객체입니다.

In the following example, two separate references are provided. The link relation of the first is unspecified, while the link relation of the second is "`thumbnail`".

다음 예에서는 두 개의 서로 다른 참조가 제공됩니다. 첫 번째 링크의 관계는 지정되지 않은 반면 두 번째 링크의 관계는 ""`thumbnail`" 입니다.

<div align="center"><em>
Figure 14
</em></div>

<div align="center" id="도표-14"><em>
도표 14
</em></div>

><div align="center"> Example 14 </div>
>
>```json
>{
>  "name": "Exampletron 3000",
>}
>```

><div align="center"> 예시 14 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Application",
>  "id": "http://example.org/application/123",
>  "name": "예시제조기 3000",
>  "image": [
>    "http://example.org/application/abc.gif",
>    {
>      "type": "Link",
>      "href": "http://example.org/application/123.png",
>      "mediaType": "image/png",
>      "rel": "thumbnail"
>    }
>  ]
>}
>```

It ought to be noted that the [[HTML5](ActivityStreams2.0ChapterF.md#html5)] specification provides its own alternative definition of a "link relation" that differs slightly from the [[RFC5988](ActivityStreams2.0ChapterF.md#rfc5988)] definition. In the HTML5 definition, any string that does not contain the "space" U+0020, "tab" (U+0009), "LF" (U+000A), "FF" (U+000C), "CR" (U+000D) or "," (U+002C) characters can be used as a valid link relation. To promote interoperability, Activity Streams 2.0 implementations *MUST* only use link relations that are syntactically valid in terms of both the [[RFC5988](ActivityStreams2.0ChapterF.md#rfc5988)] and [[HTML5](ActivityStreams2.0ChapterF.md#html5)] definitions. Implementations *MAY* use link relation values that are not registered.

[[HTML5](ActivityStreams2.0ChapterF.md#html5)] 사양은 [[RFC5988](ActivityStreams2.0ChapterF.md#rfc5988)] 정의와 약간 다른 "링크 관계"에 대한 자체적인 대체 정의를 제공한다는 점에 유의해야 합니다. HTML5 정의에서 "space" U+0020, "tab"(U+0009), "LF"(U+000A), "FF"(U+000C), "CR"(U+000D) 또는 ""(U+002C) 문자를 포함하지 않는 문자열을 유효한 링크 관계로 사용할 수 있습니다. 상호 운용성을 향상시키려면 Activity Streams 2.0 구현에서 [[RFC5988](ActivityStreams2.0ChapterF.md#rfc5988)] 및 [[HTML5](ActivityStreams2.0ChapterF.md#html5)] 정의의 관점에서 *반드시* 구문적으로 유효한 링크 관계만 사용해야 합니다. 구현에서는 등록되지 않은 링크 관계 값을 사용 *할 수도* 있습니다.

Note that the [Link](#42-링크-link) and [Object](#41-객체-object) types are disjoint from one another. That is, any given [Object](#41-객체-object) cannot also be a [Link](#42-링크-link).

[Link](#42-링크-link) 타입과 [Object](#41-객체-object) 타입은 서로 분리되어 있는 점을 유의하시길 바랍니다. 즉, 어떠한 [Object](#41-객체-object)도 [Link](#42-링크-link)가 될 수 없습니다.

### 4.3 [액터 (Actor)](#4-모델-model)

Actor objects are specializations of the base [Object](#41-객체-object) type that represent entities capable of carrying out an Activity. The [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) provides the normative definition of five specific types of Actors:

액터 객체는 Activity을 수행할 수 있는 개체를 나타내는 기본 [Object](#41-객체-object) 타입의 특수화된 경우 입니다. Activity 어휘는 다섯 가지 타입의 액터에 대한 규범적인 정의를 제공합니다:
 [Application](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-application) |
 [Group](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-group) |
 [Organization](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-organization) |
 [Person](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-person) |
 [Service](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-service).

This specification intentionally defines Actors in only the most generalized way, stopping short of defining semantically specific properties for each. All Actor objects are specializations of [Object](#41-객체-object) and inherit all of the core properties common to all Objects. External vocabularies can be used to express additional detail not covered by the Activity Vocabulary. VCard [ [vcard-rdf](ActivityStreams2.0ChapterF.md#vcard-rdf)] *SHOULD* be used to provide additional metadata for [Person](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-person), [Group](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-group), and [Organization](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-organization) instances.

이 사양은 의도적으로 액터(Actors)를 가장 일반화된 방식으로만 정의하며, 각 Actor에 대해 의미론적으로 세부적인 특정 속성들을 정의하지는 않습니다. 모든 Actor 객체는 [Object](#41-객체-object)의 특수화된 경우이며 모든 Objects에 공통되는 모든 핵심 속성들을 상속합니다. 외부 어휘를 사용하여 Activity 어휘에서 다루지 않는 추가 세부 정보를 표현할 수 있습니다. VCard [ [vcard-rdf](ActivityStreams2.0ChapterF.md#vcard-rdf)]를 사용하여 [Person](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-person), [Group](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-group) 및 [Organization](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-organization) 인스턴스에 추가 메타데이터를 *제공해야 합니다*.

<div align="center"><em>
Figure 15 An Activity with a Person actor extended with VCard properties:
</em></div>

<div align="center" id="도표-15-vcard-속성으로-확장된-person-액터가-있는-액티비티"><em>
도표 15 vCard 속성으로 확장된 Person 액터가 있는 액티비티:
</em></div>

><div align="center"> Example 15 </div>
>
>```json
>{
>  "summary": "Sally created a note",
>    "content": "This is a simple note"
>}
>```

><div align="center"> 예시 15 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {"vcard": "http://www.w3.org/2006/vcard/ns#"}
>  ],
>  "summary": "Sally는 노트를 생성했습니다",
>  "type": "Create",
>  "actor": {
>    "type": ["Person", "vcard:Individual"],
>    "id": "http://sally.example.org",
>    "name": "Sally Smith",
>    "vcard:given-name": "Sally",
>    "vcard:family-name": "Smith"
>  },
>  "object": {
>    "type": "Note",
>    "content": "이것은 간단한 노트입니다"
>  }
>}
>```

While implementations are free to introduce new types of Actors beyond those defined by the Activity Vocabulary, interoperability issues can arise when applications rely too much on extension types that are not recognized by other implementations. Care should be taken to not unduly overlap with or duplicate the existing Actor types.

구현은 Activity 어휘에서 정의한 것 이상의 새로운 타입의 액터를 자유롭게 도입할 수 있지만, 어플리케이션이 다른 구현에서 인식하지 못하는 확장 타입에 너무 많이 의존할 경우 상호 운용성 문제가 발생할 수 있습니다. 기존 액터 타입과 과도하게 겹치거나 중복되지 않도록 주의해야 합니다.

When an implementation uses an extension type that overlaps with a core vocabulary type, the implementation *MUST* also specify the core vocabulary type. For instance, some vocabularies (e.g. VCard) define their own types for describing people. An implementation that wishes, for example, to use a `vcard:Individual` as an Actor *MUST* also identify that Actor as a [Person](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-person) as illustrated in the previous example.

구현에서 핵심 어휘 타입과 겹치는 확장 타입을 사용하는 경우, 구현에서는 *반드시* 핵심 어휘 타입도 지정해야 합니다. 예를 들어, 일부 어휘(예: VCard)는 사용자를 설명하기 위한 고유한 타입을 정의합니다. 예를 들어, `vcard:Individual`를 액터로 사용하고자 하는 구현은 이전의 예시처럼 *반드시* 액터를 [Person](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-person)으로 식별해야 합니다.

### 4.4 [액티비티 (Activity)](#4-모델-model)

Activity objects are specializations of the base [Object](#41-객체-object) type that provide information about actions that have either already occurred, are in the process of occurring, or may occur in the future.

Activity 객체는 이미 발생했거나 현재 발생 중이거나 향후 발생할 수 있는 작업에 대한 정보를 제공하는 기본 [Object](#41-객체-object) 타입의 특수화된 경우입니다.

In addition to common properties supported by all [Object](#41-객체-object) instances, Activity objects support the following additional properties defined by the [Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/):

모든 [Object](#41-객체-object) 인스턴스가 지원하는 공통 속성 외에도 Activity 객체는 [어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 의해 정의된 다음과 같은 추가 속성을 지원합니다:
 [actor](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-actor) |
 [object](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-object-term) |
 [target](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-target) |
 [origin](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-origin) |
 [result](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-result) |
 [instrument](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-instrument)

The `type` property is used to identify the type of action the Activity Statement represents.

`type` 속성은 Activity 정책이 나타내는 행동의 타입을 식별하는 데 사용됩니다.

<div align="center"><em>
Figure 16 The following example illustrates a simple Activity:
</em></div>

<div align="center" id="도표-16-다음-예시는-간단한-액티비티를-보여준다"><em>
도표 16 다음 예시는 간단한 액티비티를 보여준다:
</em></div>

><div align="center"> Example 16 </div>
>
>```json
>{
>  "summary": "Joe liked a note",
>}
>```

><div align="center"> 예시 16 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Joe는 노트를 좋아했습니다",
>  "type": "Like",
>  "id": "http://www.test.example/activity/1",
>  "actor": "http://example.org/profiles/joe",
>  "object": "http://example.com/notes/1",
>  "published": "2014-09-30T12:34:56Z"
>}
>```

The [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) defines a small number of `Activity` types that are common to many social Web applications. This specification stops short of defining semantically specific properties for most of these activities. External vocabularies can be used to express additional detail not covered by the Activity Vocabulary.

[Activity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)는 많은 소셜 웹 어플리케이션에 공통적인 소수의 `Activity` 타입을 정의합니다. 이 사양은 이러한 대부분의 액티비티(activities)에 대해 의미론적으로 세부적인 특정 속성들을 정의하지는 않습니다. 외부 어휘를 사용하여 Activity 어휘에서 다루지 않는 추가 세부 정보를 표현할 수 있습니다.

While implementations are free to introduce new types of Activites beyond those defined by the Activity Vocabulary, interoperability issues can arise when applications rely too much on extension types that are not recognized by other implementations. Care should be taken to not unduly overlap with or duplicate the existing Activity types.

구현 시 Activity 어휘에서 정의한 것과 다른, 새로운 타입의 Activity들을 자유롭게 도입할 수 있지만, 어플리케이션이 다른 구현에서 인식하지 못하는 확장 타입에 너무 많이 의존할 경우 상호 운용성 문제가 발생할 수 있습니다. 기존 Activity 타입과 과도하게 겹치거나 중복되지 않도록 주의해야 합니다.

When an implementation uses an extension type that overlaps with a core vocabulary type, the implementation *MUST* also specify the core vocabulary type. For instance, some vocabularies (e.g. Schema.org) define their own types for describing actions. An implementation that wishes, for example, to use http://schema.org/LikeAction as an Activity *MUST* also identify that Object as being a [Like](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-like) as illustrated in the following:

구현에서 핵심 어휘 타입과 겹치는 확장 타입을 사용하는 경우 구현에서는 *반드시* 핵심 어휘 타입도 지정해야 합니다. 예를 들어, 일부 어휘(예: Schema.org)는 작업을 설명하기 위한 고유한 타입을 정의합니다. 예를 들어, http://schema.org/LikeAction을 Activity으로 사용하고자 하는 구현에서는 *반드시*  다음 도표와 같이 해당 객체를 [Like](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-like) 객체로도 식별해야 합니다.

<div align="center"><em>
Figure 17 An Activity that is both a <a href="https://www.w3.org/TR/activitystreams-vocabulary/#dfn-like">Like</a> and a <code>http://schema.org/LikeAction:</code>
</em></div>

<div align="center" id="도표-17-like이면서-httpschemaorglikeaction인-액티비티"><em>
도표 17 <a href="https://www.w3.org/TR/activitystreams-vocabulary/#dfn-like">Like</a>이면서 <code>http://schema.org/LikeAction</code>인 액티비티:
</em></div>

><div align="center"> Example 17 </div>
>
>```json
>{
>  "summary": "Joe liked a note",
>}
>```

><div align="center"> 예시 17 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Joe는 노트를 좋아했습니다",
>  "type": ["Like", "http://schema.org/LikeAction"],
>  "id": "http://www.test.example/activity/1",
>  "actor": "http://example.org/profiles/joe",
>  "object": "http://example.com/notes/1",
>  "published": "2014-09-30T12:34:56Z"
>}
>```

Implementations are free to use Activity objects in both passive and imperative operations. In the passive sense, the Activity is used to record that an activity has or is occurring. In the imperative sense, the Activity can be used as a form of command, instructing an application to modify state in some manner consistent with the action being described. However, because this specification does not define a normative processing model that constrains how applications make use of the format, the distinction about whether an Activity statement is to be interpreted as a passive notification or as an imperative command can vary across implementations.

구현 시 수동적인 작업과 필수적인 작업 모두 Activity 객체를 자유롭게 사용할 수 있습니다. 수동적 의미에서는 Activity를 사용하여 액티비티가 있거나 발생 중임을 기록합니다. 필수적인 의미에서의 Activity는 명령의 한 형태로 사용될 수 있으며, 묘사되는 행동과 같은 방식으로 상태를 수정하도록 응용 프로그램에 지시할 수 있습니다. 그러나 이 사양은 어플리케이션이 형식을 사용하는 방법을 제한하는 표준 처리 모델을 정의하지 않기 때문에, Activity 문을 수동적인 의미로 해석해야 하는지 필수적인 명령으로 해석해야 하는지에 대한 구분은 구현에 따라 다를 수 있습니다.

[//TODO]: # "액티비티? Activity? 행동? 재검토가 필요할것 같습니다"

### 4.5 [비-과도적 액티비티 (IntransitiveActivity)](#4-모델-model)

IntransitiveActivity objects are specializations of the [Activity](#44-액티비티-activity) type that represent intransitive actions. IntransitiveActivity objects do not have an [object](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-object-term) property.

InteractiveActivity 객체는 비-과도적인 행동을 나타내는 [Activity](#44-액티비티-activity) 타입의 특수화된 경우입니다. InteractiveActivity 객체에는 [object](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-object-term) 속성이 없습니다.

[//Comment]: # "Activity-어휘처럼 의미상으론 '완전히 끝난', '진행중이지 않은'으로 해석하는것도 올바르다고 보나, 사용처가 적기 때문에 간략하게 '비-과도적'이라 번역했습니다."

### 4.6 [컬렉션 (Collection)](#4-모델-model)

`Collection` objects are a specialization of the base [Object](#41-객체-object) that serve as a container for other [Objects](#41-객체-object) or [Links](#42-링크-link).

`Collection` 객체는 다른 [Objects](#41-객체-object) 또는 [Links](#42-링크-link)의 컨테이너 역할을 하는 기본 [Object](#41-객체-object)의 특수화된 경우입니다.

In addition to the base properties inherited by all [Objects](#41-객체-object), all [Collection](#46-컬렉션-collection) types contain the additional properties:

모든 [Objects](#41-객체-object)에서 상속된 기본 속성 외에 모든 [Collection](#46-컬렉션-collection) 타입에는 다음과 같은 추가 속성이 포함됩니다:
 [items](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-items) |
 [totalItems](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-totalitems) |
 [first](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-first) |
 [last](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-last) |
 [current](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-current)

The items within a [Collection](#46-컬렉션-collection) can be ordered or unordered. The _**`OrderedCollection`**_ type *MAY* be used to identify a Collection whose items are always ordered. In the JSON serialization, the unordered items of a Collection are represented using the `items` property while ordered items are represented using the `orderedItems` property.

[Collection](#46-컬렉션-collection)의 항목은 정렬되거나 정렬되지 않을 수 있습니다. <dfn id="orderedcollection">_**`OrderedCollection`**_</dfn> 타입은 항상 주문되는 품목을 식별하는 데 사용 *할 수도* 있습니다. JSON 직렬화에서 컬렉션의 정렬되지 않은 항목둘은 `items` 속성을 사용하여 표시되고 정렬된 항목은 `orderedItems` 속성을 사용하여 표시됩니다.

<div align="center"><em>
Figure 18 The following is a simple unordered collection:
</em></div>

<div align="center" id="도표-18-다음은-간단한-정렬되지-않은-컬렉션이다"><em>
도표 18 다음은 간단한 정렬되지 않은 컬렉션이다:
</em></div>

><div align="center"> Example 18 </div>
>
>```json
>{
>  "summary": "Object history",
>}
>```

><div align="center"> 예시 18 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "객체 히스토리",
>  "type": "Collection",
>  "totalItems": 2,
>  "items": [
>    {
>      "type": "Create",
>      "actor": "http://www.test.example/sally",
>      "object": "http://example.org/foo"
>    },
>    {
>      "type": "Like",
>      "actor": "http://www.test.example/joe",
>      "object": "http://example.org/foo"
>    }
>  ]
>}
>```

<div align="center"><em>
Figure 19 The following is a simple ordered collection:
</em></div>

<div align="center"><em>
도표 19 다음은 간단한 정렬된 컬렉션이다:
</em></div>

><div align="center"> Example 19 </div>
>
>```json
>{
>  "summary": "Object history",
>}
>```

><div align="center" id="도표-19-다음은-간단한-정렬된-컬렉션이다"> 예시 19 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "객체 히스토리",
>  "type": "OrderedCollection",
>  "totalItems": 2,
>  "orderedItems": [
>    {
>      "type": "Create",
>      "actor": "http://www.test.example/sally",
>      "object": "http://example.org/foo"
>    },
>    {
>      "type": "Like",
>      "actor": "http://www.test.example/joe",
>      "object": "http://example.org/foo"
>    }
>  ]
>}
>```

### 4.6.1 [컬렉션 페이징 (Collection Paging)](#46-컬렉션-collection)

A Collection can contain a large number of items. Often, it becomes impractical for an implementation to serialize every item contained by a Collection using the `items` (or `orderedItems`) property alone. In such cases, the items within a Collection can be divided into distinct subsets or "pages". A page is identified using the _**`CollectionPage`**_ type.

컬렉션에는 많은 수의 항목들이 포함될 수 있습니다. 종종 `items`(또는 `orderedItems`) 속성만 사용하여 컬렉션에 포함된 모든 항목을 직렬화하는 구현은 비-실용적입니다. 이러한 경우, 컬렉션 내의 항목을 고유한 하위 집합 또는 "페이지(pages)"로 나눌 수 있습니다. 페이지는 <dfn id="collectionpage">_**`CollectionPage`**_</dfn> 타입을 사용하여 식별합니다.

The [`CollectionPage`](#collectionpage) type extends from the base [Collection](#46-컬렉션-collection) type and inherits all of it's properties. The following additional properties can also be specified:

[`CollectionPage`](#collectionpage) 타입은 기본 [Collection](#46-컬렉션-collection) 타입에서 확장되었으며 해당 타입의 모든 속성을 상속합니다. 다음과 같은 추가 속성들도 지정할 수 있습니다:
 [partOf](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-partof) |
 [next](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-next) |
 [prev](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-prev) |

The `partOf` property identifies the [Collection](#46-컬렉션-collection) to which the items contained by the `CollectionPage` belong.

`partOf` 속성은 `CollectionPage`에 포함된 항목이 속한 [Collection](#46-컬렉션-collection)을 식별합니다.

The `first`, `next`, `prev`, `last`, and `current` properties are used to reference other [`CollectionPage`](#collectionpage) instances that contain additional subsets of items from the parent collection.

`first`, `next`, `prev`, `last`, 그리고 `current` 속성은 상위 컬렉션에서 항목의 추가 하위 집합을 포함하는 다른 [`CollectionPage`](#collectionpage) 인스턴스를 참조하는 데 사용됩니다.

As with `Collection` objects, the items within a `CollectionPage` might be ordered or unordered. The _**`OrderedCollectionPage`**_ type *MAY* be used to identify a page whose items are strictly ordered.

`Collection` 객체와 마찬가지로 `CollectionPage` 내의 항목은 정렬되거나 정렬되지 않을 수 있습니다. <dfn id="orderedcollectionpage">_**`OrderedCollectionPage`**_</dfn> 타입은 항목이 엄격하게 정렬된 페이지를 식별하는 데 사용 *할 수도* 있습니다.

The [`OrderedCollectionPage`](#orderedcollectionpage) type extends from both [`CollectionPage`](#collectionpage) and [`OrderedCollection`](#orderedcollection) . In addition to the properties inherited from each of those, the `OrderedCollectionPage` may contain an additional [startIndex](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-startindex) property whose value indicates the relative index position of the first item contained by the page within the `OrderedCollection` to which the page belongs.

[`OrderedCollectionPage`](#orderedcollectionpage) 타입은 [`CollectionPage`](#collectionpage) 와 [`OrderedCollection`](#orderedcollection) 에서 확장됩니다 . `OrderCollectionPage`에는 각 속성에서 상속된 속성 외에도 값이 페이지가 속한 `OrderCollection` 내의 페이지에 포함된 첫 번째 항목의 상대적인 인덱스 위치를 나타내는 인덱스 속성인 [startIndex](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-startindex)를 포함할 수도 있습니다.

<div align="center"><em>
Figure 20 An illustration of the relationship between
 <code>Collection</code>,
 <code>OrderedCollection</code>,
 <code>CollectionPage</code>, and
 <code>OrderedCollectionPage</code>:
</em></div>

<div align="center" id="도표-20-collection-orderedcollection-collectionpage및-orderedcollectionpage-간의-관계에-대한-그림"><em>
도표 20
 <code>Collection</code>,
 <code>OrderedCollection</code>,
 <code>CollectionPage</code>, 와
 <code>OrderedCollectionPage</code>
 간의 관계에 대한 그림:
</em></div>

![컬렉션 타입 모델](./img/paging2.png)

~~[Collection type Model](./img/paging2.png)~~

[//Link]: # "https://www.w3.org/TR/activitystreams-core/paging2.png"

Whether ordered or not, the pages of a `Collection` are typically arranged in a sequence (either a singly or doubly-linked list). The `first` property is used to identify the first page in this sequence, while the `last` property is used to identify the final page in the sequence. The `prev` and `next` properties identify the pages immediately before and immediately following, respectively.

순서 여부에 관계없이 `Collection`의 페이지들은 일반적으로 (단일 또는 이중 연결 리스트를 사용하여) 순서대로 정렬됩니다. `first` 속성은 이 시퀀스의 첫 페이지를 식별하는 데 사용되는 반면 `last` 속성은 시퀀스의 마지막 페이지를 식별하는 데 사용됩니다. `prev` 속성과 `next` 속성은 각각 직전과 직후의 페이지를 식별합니다.

<div align="center"><em>
Figure 21 A visualization of the Collection paging model:
</em></div>

<div align="center" id="도표-21-컬렉션-페이징-모델의-시각화"><em>
도표 21 컬렉션 페이징 모델의 시각화:
</em></div>

![페이징 모델](./img/paging.png)

~~[The Paging Model](https://www.w3.org/TR/activitystreams-core/paging.png)~~

[//Link]: # "https://www.w3.org/TR/activitystreams-core/paging2.png"

The `current` property identifies a page containing the subset of items in the `Collection` that have been created or updated most recently.

`current` 속성은 `Collection`에서 가장 최근에 생성되거나 업데이트된 항목의 하위 집합을 포함하는 페이지를 식별합니다.

The values for the `first`, `last`, `next`, `prev`, and `current` properties can be either a single [`CollectionPage`](#collectionpage) or a [Link](#42-링크-link) referencing a separate resource containing a [`CollectionPage`](#collectionpage) .

 `first`, `last`, `next`, `prev`, 그리고 `current`의 값은 단일 [`CollectionPage`](#collectionpage) 또는 [`CollectionPage`](#collectionpage) 가 포함된 별도의 리소스를 참조하는 [Link](#42-링크-link)일 수 있습니다.

<div align="center"><em>
Figure 22 The following is a simple unordered collection with paging:
</em></div>

<div align="center" id="도표-22-다음은-페이징이-있는-간단한-정렬되지-않은-컬렉션이다"><em>
도표 22 다음은 페이징이 있는 간단한 정렬되지 않은 컬렉션이다:
</em></div>

><div align="center"> Example 20 </div>
>
>```json
>{
>  "summary": "Sally's recent activities",
>}
>```

><div align="center"> 예시 20 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Sally의 최근 활동",
>  "type": "Collection",
>  "id": "http://example.org/foo",
>  "totalItems": 10,
>  "first": {
>    "type": "CollectionPage",
>    "id": "http://example.org/foo?page=1",
>    "partOf": "http://example.org/foo",
>    "next": "http://example.org/foo?page=2",
>    "items": [
>      {
>        "type": "Create",
>        "actor": "http://www.test.example/sally",
>        "object": "http://example.org/foo"
>      }
>    ]
>  }
>}
>```

Using paging with an `OrderedCollection` can be tricky because there are no guarantees that implementations will process the sequence of pages in any predictable order. Implementations that wish to reconstruct the appropriate complete ordering of member items in the logical collection should navigate to the first (or last) page in the sequence then recursively follow the `next` (or `prev`) link until all pages have been processed. The pages of an `OrderedCollection` *SHOULD* be instances of `OrderedCollectionPage`. If the pages of an `OrderedCollection` are not instances of `OrderedCollectionPage`, a consumer will have no reliable means of reconstructing the appropriate ordering of items.

`OrderedCollection`과 함께 페이징을 사용하는 것은, 구현이 페이지 순서를 예측 가능한 순서로 처리한다는 보장이 없기 때문에 어려울 수 있습니다. 논리적 컬렉션에서 구성원 항목의 적절한 전체 순서를 재구성하려는 구현은 첫 번째(또는 마지막) 페이지로 이동한 후 모든 페이지가 처리될 때까지 `next` (또는 `prev`) 링크를 반복적으로 따라가야 합니다. `OrderedCollection`의 페이지는 `OrderedCollectionPage`의 *인스턴스여야 합니다*. `OrderedCollection`의 페이지가 `OrderedCollectionPage`의 인스턴스가 아닌 경우, 소비자는 항목의 순서를 적절하게 재구성할 수 있는 신뢰할만한 수단이 없어집니다.

### 4.7 [자연어 값 (Natural Language Values)](#4-모델-model)

Several properties defined by the [Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) are defined as having natural language values. These are human-readable strings using one or more languages. Within the JSON serialization, they are expressed as either (1) a single JSON string or (2) a JSON object mapping well-formed [[BCP47](ActivityStreams2.0ChapterF.md#bcp47)] Language-Tags to localized, equivalent translations of the same string value. In the serialized JSON, these two forms are differentiated using a simple property naming convention, for instance: "`name`" identifies the JSON string form for the [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) property while "`nameMap`" represents the object form.

[어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 의해 정의된 몇 가지 속성은 자연어 값을 갖는 것으로 정의됩니다. 이는 사람이 읽을 수 있는 하나 이상의 언어를 사용한 문자열입니다. JSON 직렬화 내에서 이러한 문자열은 (1) 단일 JSON 문자열 또는 (2) 잘 만들어진 [[BCP47](ActivityStreams2.0ChapterF.md#bcp47)] 언어 태그를 이와 동등한 문자열 값의 현지화된 번역을 JSON 객체로 매핑하는 것으로 표현됩니다. 직렬화된 JSON에서는 간단한 속성 이름 지정 규칙을 사용하여 두 가지 양식을 구분합니다. 예를 들어, "`name`"은 [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name) 속성에 대한 JSON 문자열 형식이고 "`nameMap`"의 경우에는 이에 대한 객체 형식입니다.

[//Comment]: # "번역이 매끄럽지 않은것 같습니다."

<div align="center"><em>
Figure 23 A single name String value without language information:
</em></div>

<div align="center" id="도표-23-언어-정보가-없는-단일-이름-문자열-값"><em>
도표 23 언어 정보가 없는 단일 이름 문자열 값:
</em></div>

><div align="center"> Example 21 </div>
>
>```json
>{
>  "name": "This is the title"
>}
>```

><div align="center"> 예시 21 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Object",
>  "name": "이것은 제목입니다"
>}
>```

<div align="center"><em>
Figure 24 Multiple, language-specific values:
</em></div>

<div align="center" id="도표-24-여러-언어별-값"><em>
도표 24 여러 언어별 값:
</em></div>

><div align="center"> Example 22 </div>

><div align="center"> 예시 22 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Object",
>  "nameMap": {
>    "en": "This is the title",
>    "fr": "C'est le titre",
>    "es": "Este es el título"
>  }
>}
>```

[//Comment]: # "nameMap이 en,fr,es로 설정되어 있으므로 따로 번역을 하지 않겠습니다."

Every key in the object form *MUST* be a well-formed [[BCP47](ActivityStreams2.0ChapterF.md#bcp47)] Language-Tag. The associated values *MUST* be strings.

객체 형식의 모든 키는 *반드시* 제대로 구성된 [[BCP47](ActivityStreams2.0ChapterF.md#bcp47)] 언어 태그 여야 합니다. 연결된 값은 *반드시* 문자열이어야 합니다.

The [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) defines three properties that use natural language values:
 [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name),
 [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary), and
 [content](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content).
Accordingly, in the JSON serialization, the terms " `name`", "`summary`", and "`content`" represent the JSON string forms; and the terms " `nameMap`", "`summaryMap`", and " `contentMap`" for represent the object forms.

Activity 어휘는 자연어 값을 사용하는 세 가지 속성을 정의합니다:
 [name](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-name),
 [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary), 그리고
 [content](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content).
 이 순서대로, JSON 직렬화에서 " `name`", "`summary`", 그리고 "`content`"이라는 용어는 JSON 문자열 양식을 나타내고, " `nameMap`", "`summaryMap`", 그리고 " `contentMap`"이라는 용어는 객체 형식을 나타냅니다.

The special language tag "`und`" can be used within the object form to explicitly identify a value whose language is unknown or undetermined.

객체 양식 내에서 특수 언어 태그 "`und`" 를 사용하여 알수 없거나 결정되지 않은 언어를 명시적으로 식별할 수 있습니다.

<div align="center"><em>
Figure 25 Using the <code>"und"</code> language tag:
</em></div>

<div align="center" id="도표-25-und-언어-태그-사용"><em>
도표 25 <code>"und"</code> 언어 태그 사용:
</em></div>

><div align="center"> Example 23 </div>
>
>```json
>{
>    "und": "This is the title"
>}
>```

><div align="center"> 예시 23 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Object",
>  "nameMap": {
>    "und": "이것은 제목입니다"
>  }
>}
>```

### 4.7.1 [기본 언어 컨텍스트 (Default Language Context)](#47-자연어-값-natural-language-values)

When using [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] mechanisms to produce or consume Activity Streams 2.0 documents, the `@language` property *MAY* be used within a `@context` to identify the default language. This mechanism may not be understood by implementations that do not choose to process Activity Streams 2.0 documents using JSON-LD.

[[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] 메커니즘을 사용하여 Activity Streams 2.0 문서를 생성하거나 사용할 경우 `@context` 내에서 `@language` 속성이 사용되어 기본 언어를 식별 *할 수도* 있습니다. JSON-LD를 사용하여 Activity Streams 2.0 문서를 처리하도록 선택하지 않은 구현에서는 이 메커니즘을 사용하지 못할 수도 있습니다.

<div align="center"><em>
Figure 26 Specifying the default <code>"@language"</code> within the JSON-LD <code>@context</code>:
</em></div>

<div align="center" id="도표-26-json-ld-context-내의-기본-language-지정"><em>
도표 26 JSON-LD <code>@context</code> 내의 기본 <code>"@language"</code> 지정:
</em></div>

><div align="center"> Example 24 </div>

><div align="center"> 예시 24 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {
>      "@language": "en"
>    }],
>  "type": "Object",
>  "name": "This is the title"
>}
>```

[//Comment]: # "@language가 en으로 설정되어 있으므로 따로 번역을 하지 않겠습니다."

### 4.7.2 [양방향 텍스트 (Bidirectional Text)](#47-자연어-값-natural-language-values)

Natural language values within an Activity Streams 2.0 document *MAY* contain bidirectional text. The default base direction of an Activity Streams 2.0 document is Left-to-Right. The base direction of individual natural language values *MAY* be modified as described below.

Activity Streams 2.0 문서의 자연어 값은 양방향 텍스트를 포함 *할 수도* 있습니다. Activity Streams 2.0 문서의 기본 기본 방향은 왼쪽에서 오른쪽으로 입니다. 개별 자연어 값의 기본 방향은 아래 설명된 대로 수정 *될 수도* 있습니다.

When specifying bidirectional text for a natural language value, and the base direction of the text cannot be correctly identified by the first strong directional character of that text, publishers *SHOULD* explicitly identify the default direction either by prefixing the value with an appropriate Unicode bidirectional control character, or by using HTML directional markup where permitted.

자연어 값에 대해 양방향 텍스트를 지정하고, 텍스트의 기본 방향을 해당 텍스트의 첫 번째 강력한 방향 문자(first strong directional character)로 올바르게 식별할 수 없는 경우, 게시자는 해당 값을 적절한 유니코드 양방향 제어 문자로 접두사 또는 HTML 방향 표시(허용되는 경우)를 사용하여 기본 방향을 명시적으로 *식별해야 합니다*.

[//Comment]: # "'first strong directional character' 를 직역하여 '첫 번째 강력한 방향 문자'로 표현하였습니다. 차후에 더 좋은 번역이 있으면 수정해주시길 바랍니다."

Consumers of Activity Streams 2.0 documents that contain bidirectional text *SHOULD* identify the base direction of any given natural language value by either scanning the text for the first strong directional character not contained within a markup tag; or by utilizing directional markup where provided. Once the base direction has been identified, consumers *MUST* determine the appropriate rendering and display of natural language values, according to the Unicode Bidirectional Algorithm [[BIDI](ActivityStreams2.0ChapterF.md#bidi)]. This may necessitate wrapping additional control characters or markup around the string prior to display, in order to apply the base direction.

양방향 텍스트를 포함하는 Activity Streams 2.0 문서의 소비자는 마크업 태그에 포함되지 않은 첫 번째 강력한 방향 문자를 텍스트 스캔하거나, 제공된 경우 방향 표시를 활용하여 주어진 자연어 값의 기본 방향을 *식별해야 합니다*. 기본 방향이 식별되면 유니코드 양방향 알고리즘 [[BIDI](ActivityStreams2.0ChapterF.md#bidi)]에 따라 소비자가 *반드시* 자연어 값의 적절한 렌더링 및 표기를 결정해야 합니다. 이 경우 기본 방향을 적용하려면 표시하기 전에 추가 컨트롤 문자를 감거나 문자열 주위에 표시해야 할 수 있습니다.

Property | Value | Direction | Method
--|--|--|--
`name` | `"פעילות הבינאום, W3C"` | Right-to-Left | First strong directional character
`name` | `"The document was titled, '\u2067פעילות הבינאום, W3C\u2069'"` | Left-to-Right | First strong directional character
`name` | `"\u200FHTML היא שפת סימון"` | Right-to-Left | Bidi Control Character
`name` | `"\u200E'سلام' is hello in Persian."` | Left-to-Right | Bidi Control Character
`summary` | `<p dir=\"rtl\">HTML היא שפת סימון>/p>` | Right-to-Left | HTML Markup
`summary` | `<p>פעילות הבינאום, W3C</p>` | Right-to-Left | First strong directional character (ignoring markup)
`summary` | `<p title="سلام">Hello</p>` | Left-to-Right | First strong directional character (ignoring markup)

속성 | 값 | 방향 | 방법
--|--|--|--
`name` | `"פעילות הבינאום, W3C"` | 오른쪽에서-왼쪽으로 | 첫 번째 강력한 방향 문자
`name` | `"The document was titled, '\u2067פעילות הבינאום, W3C\u2069'"` | 왼쪽에서-오른쪽으로 | 첫 번째 강력한 방향 문자
`name` | `"\u200FHTML היא שפת סימון"` | 오른쪽에서-왼쪽으로 | Bidi 제어 문자
`name` | `"\u200E'سلام' is hello in Persian."` | 왼쪽에서-오른쪽으로 | Bidi 제어 문자
`summary` | `<p dir=\"rtl\">HTML היא שפת סימון>/p>` | 오른쪽에서-왼쪽으로 | HTML 마크업
`summary` | `<p>פעילות הבינאום, W3C</p>` | 오른쪽에서-왼쪽으로 | 첫 번째 강력한 방향 문자 (마크업 무시)
`summary` | `<p title="سلام">Hello</p>` | 왼쪽에서-오른쪽으로 | 첫 번째 강력한 방향 문자 (마크업 무시)

### 4.8 [언어 표기 (Marking up language)](#4-모델-model)

Activity Streams 2.0 publishers *SHOULD* explicitly mark the language of natural language properties if they are known, using either map properties or a default language tag.

Activity Streams 2.0 게시자는 지도 속성 또는 기본 언어 태그가 알려진 경우, 이를 사용하여 자연어 속성의 언어를 *명시적으로 표시해야 합니다*.

>Note: Examples
>
>Not all examples in this specification explicitly mark the language of natural language properties. This is intentional. The authors and the working group wished to avoid having implementers cut-and-paste examples from the document with explicit language markup as a template for new documents, which would consequently have inaccurate language markup.

>참고: 예시
>
>이 사양의 모든 예제가 자연어 속성의 언어를 명시적으로 표시하는 것은 아닙니다. 이것은 의도적인 행위입니다. 저자와 작업 그룹은 새로운 문서의 템플릿으로 결과론적으로 언어 표기가 부정확할 수 있는, 이 문서의 명시적 언어 표기 예시를 그대로 가져가 사용할수 있는 가능성을 배제하고자 했습니다.

[맨 위로](#4-모델-model)
