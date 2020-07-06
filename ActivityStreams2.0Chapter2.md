[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 2. [직렬화 (Serialization)](ActivityStreams2.0Contents.md#목차-table-of-contents)

This specification describes a JSON-based [[RFC7159](ActivityStreams2.0ChapterF.md#rfc7159)] serialization syntax for the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) that conforms to a subset of [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] syntax constraints but does not require JSON-LD processing. While other serialization forms are possible, such alternatives are not discussed by this document.

이 사양에서는 [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] 구문 제약 조건의 하위 집합을 준수하지만 JSON-LD 처리가 필요 없는 [Activity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 대한 JSON 기반 [[RFC7159](ActivityStreams2.0ChapterF.md#rfc7159)] 직렬화 구문을 설명합니다. 다른 직렬화 양식도 가능하지만, 이러한 대체 양식은 본 문서에서 다루지 않습니다.

When serialized, absent properties are represented by either (a) setting the property value to null, or (b) by omitting the property declaration altogether at the option of the publisher. These representations are semantically equivalent. If a property has an array value, the absence of any items in that array *MUST* be represented by omitting the property entirely or by setting the value to null. The appropriate interpretation of an omitted or explicitly null value is that no value has been assigned as opposed to the view that the given value is empty or nil.

직렬화할 때 비어있는 속성들은 (a) 속성 값을 null로 설정하거나 (b) 게시자의 옵션에서 속성 선언을 모두 생략하여 표시합니다. 이러한 표현은 어느쪽이나 의미론적으로는 동일합니다. 속성에 배열 값이 존재하는 경우, 해당 배열에 비어있는 항목의 속성을 *반드시* 완전히 생략하거나 값을 null로 설정하여 표시해야 합니다. 생략되거나 명시적으로 null 값에 대한 적절한 해석은 지정된 값이 비어 있거나 nil이라는 견해가 아닌, 할당된 값이 없다는 것입니다.

An _**Activity Streams Document**_ is a JSON document whose root value is an Activity Streams [Object](ActivityStreams2.0Chapter4.md#41-객체-object) of any type, including a [Collection](ActivityStreams2.0Chapter4.md#46-컬렉션-collection), and whose MIME media type is " `application/activity+json`".

_**Activity Streams 문서**_ 는 기반 값이 [Collection](ActivityStreams2.0Chapter4.md#46-컬렉션-collection)을 포함한 모든 유형의 Activity Streams [Object](ActivityStreams2.0Chapter4.md#41-객체-object)이며, 이것의 MIME 미디어 타입은 " `application/activity+json`"입니다.

Activity Streams 2.0 documents *MUST* be serialized using the UTF-8 character encoding.

Activity Streams 2.0 문서는 *반드시* UTF-8 문자 인코딩을 사용하여 직렬화해야 합니다.

### 2.1 [JSON-LD](#2-직렬화-serialization)

The serialized JSON form of an Activity Streams 2.0 document *MUST* be consistent with what would be produced by the standard JSON-LD 1.0 Processing Algorithms and API [[JSON-LD-API](ActivityStreams2.0ChapterF.md#json-ld-api)] Compaction Algorithm using, at least, the normative JSON-LD @context definition provided [here](https://www.w3.org/ns/activitystreams). Implementations *MAY* augment the provided @context with additional @context definitions but *MUST NOT* override or change the normative context. Implementations *MAY* also use additional properties and values not defined in the JSON-LD @context with the understanding that any such properties will likely be unsupported and ignored by consuming implementations that use the standard JSON-LD algorithms. See the [Extensibility](ActivityStreams2.0Chapter5.md) section for more information on handling extensions within Activity Streams 2.0 documents.

Activity Streams 2.0 문서의 직렬화된 JSON 양식은 표준 JSON-LD 1.0 처리 알고리즘과 최소한 [여기](https://www.w3.org/ns/activitystreams)에서 제공된 표준 JSON-LD @context의 정의 같은 정의를 사용한 API [[JSON-LD-API](ActivityStreams2.0ChapterF.md#json-ld-api)] 압축 알고리즘에 의해 생성될 내용은 *반드시* 일관적이여야 합니다. 구현 시 제공된 @context를 추가 @context 정의로 확장 *할 수도* 있지만 규범적인 컨텍스트를 재 정의하거나 변경해서는 *절대 안 됩니다*. 또한 구현은 표준 JSON-LD 알고리즘을 사용하는 구현을 사용함으로써 JSON-LD @context에 정의되지 않은 추가 속성과 값이 지원되지 않거나 무시될 수 있음을 인지하면서 사용 *할 수도* 있습니다. Activity Streams 2.0 문서의 확장자 처리에 대한 자세한 내용은 [확장성](ActivityStreams2.0Chapter5.md) 섹션을 참조하시길 바랍니다.

JSON-LD uses the special `@context` property to define the [processing context](http://www.w3.org/TR/json-ld/#the-context). The value of the `@context` property is defined by the [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] specification. Implementations producing Activity Streams 2.0 documents *SHOULD* include a `@context` property with a value that includes a reference to the normative [Activity Streams 2.0 JSON-LD @context definition](https://www.w3.org/ns/activitystreams) using the URL " `https://www.w3.org/ns/activitystreams`". Implementations *MAY* use the alternative URL " `http://www.w3.org/ns/activitystreams`" instead. This can be done using a string, object, or array.

JSON-LD는 특수한 `@context` 속성을 사용하여 [컨텍스트 처리](http://www.w3.org/TR/json-ld/#the-context)를 정의합니다. `@context` 속성의 값은 [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] 규격에 의해 정의됩니다. Activity Streams 2.0 문서를 생성하는 구현에는 "https://www.w3.org/ns/activitystreams" URL 을 사용하는 규범적 [Activity Streams 2.0 JSON-LD @properties 정의](https://www.w3.org/ns/activitystreams)에 대한 참조를 포함하는 값 이 들어가 있는 `@context` 속성을 *포함해야 합니다*. 구현에서는 대체 URL "http://www.w3.org/ns/activitystreams" 을 대신 사용 *할 수도* 있습니다. 문자열, 개체 또는 배열을 사용하여 이 작업을 수행할 수 있습니다.

### 2.1.1 [문자열이 있는 컨텍스트 (Context with a string)](#21-json-ld)

<div align="center"><em>
Figure 1 Document providing a context as a string.
</em></div>

<div align="center" id="도표-1-컨텍스트를-문자열로-제공하는-문서"><em>
도표 1 컨텍스트를 문자열로 제공하는 문서.
</em></div>

><div align="center"> Example 1 </div>
>
>```json
>{
>  "summary": "A note",
>  "content": "My dog has fleas."
>}
>```

><div align="center"> 예시 1 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "노트",
>  "type": "Note",
>  "content": "제 개에 벼룩이 있어요."
>}
>```

### 2.1.2 [객체가 있는 컨텍스트 (Context with an object)](#21-json-ld)

<div align="center"><em>
Figure 2 Document providing context as an object using the <code>@vocab</code> keyword and a prefix for extension terms.
</em></div>

<div align="center" id="도표-2-vocab-키워드와-확장-용어의-접두사를-사용하여-컨텍스트를-객체로-제공하는-문서"><em>
도표 2 `@vocab` 키워드와 확장 용어의 접두사를 사용하여 컨텍스트를 객체로 제공하는 문서.
</em></div>

><div align="center"> Example 2 </div>

><div align="center"> 예시 2 </div>
>
>```json
>{
>  "@context": {
>     "@vocab": "https://www.w3.org/ns/activitystreams",
>     "ext": "https://canine-extension.example/terms/",
>     "@language": "en"
>  },
>  "summary": "A note",
>  "type": "Note",
>  "content": "My dog has fleas.",
>  "ext:nose": 0,
>  "ext:smell": "terrible"
>}
>```

[//Comment]: # "@language가 en으로 설정되어 있으므로 summary/content을 번역 해도 되는지 확실하지 않으므로 번역을 하지 않겠습니다."

### 2.1.3 [배열이 있는 컨텍스트 (Context with an array)](#21-json-ld)

<div align="center"><em>
Figure 3 Document providing context as an array, and including an alias for an additional term.
</em></div>

<div align="center" id="도표-3-컨텍스트를-배열로-제공하고-추가-용어에-대한-별칭을-포함하는-문서"><em>
도표 3 컨텍스트를 배열로 제공하고 추가 용어에 대한 별칭을 포함하는 문서.
</em></div>

><div align="center"> Example 3 </div>
>
>```json
>{
>  "summary": "A note",
>  "content": "My dog has fleas.",
>}
>```

><div align="center"> 예시 3 </div>
>
>```json
>{
>  "@context": [
>     "https://www.w3.org/ns/activitystreams",
>     {
>      "css": "http://www.w3.org/ns/oa#styledBy"
>     }
>  ],
>  "summary": "노트",
>  "type": "Note",
>  "content": "제 개에 벼룩이 있어요.",
>  "css": "http://www.csszengarden.com/217/217.css?v=8may2013"
>}
>```

When a JSON-LD enabled Activity Streams 2.0 implementation encounters a JSON document identified using the " `application/activity+json`" MIME media type, and that document does not contain a `@context` property whose value includes a reference to the normative [Activity Streams 2.0 JSON-LD @context definition](https://www.w3.org/ns/activitystreams), the implementation *MUST* assume that the normative @context definition still applies.

JSON-LD 가 활성화된 Activity Streams 2.0 구현이 표준 [Activity Streams 2.0 JSON-LD @context 정의](https://www.w3.org/ns/activitystreams)에 대한 참조가 포함된 `@context` 속성이 포함되어 있지 않은, " `application/activity+json`" MIME 미디어 타입을 사용하여 식별된 JSON 문서를 만날 경우, 구현은 *반드시* 규정의 @context 정의가 적용되고 있다고 가정해야 합니다.

### 2.2 [IRI와 URL (IRIs and URLs)](#2-직렬화-serialization)

This specification uses IRIs [[RFC3987](ActivityStreams2.0Chapter4.md#rfc3987)]. Every URI [[RFC3986](ActivityStreams2.0Chapter4.md#rfc3986)] is also an IRI, so a URI may be used wherever an IRI is named. There are two special considerations: (1) when an IRI that is not also a URI is given for dereferencing, it *MUST* be mapped to a URI using the steps in Section 3.1 of [[RFC3987](ActivityStreams2.0Chapter4.md#rfc3987)] and (2) when an IRI is serving as an "id" value, it *MUST NOT* be so mapped.

이 사양은 IRI [[RFC3987](ActivityStreams2.0Chapter4.md#rfc3987)] 를 사용합니다. 모든 URI [RFC3986]((ActivityStreams2.0Chapter4.md#rfc3986)) 도 IRI이므로 IRI가 명명된 모든 곳에서 URI를 사용할 수 있습니다. 두가지 특별한 고려 사항이 있는데: (1) URI가 아닌 IRI가 역참조를 위해 제공된 경우 [[RFC3987](ActivityStreams2.0Chapter4.md#rfc3987)]의 섹션 3.1에 기술된 단계를 사용하여 URI에 매핑되어야 하며, (2) IRI가 "id" 값으로 사용되는 경우 *절대 매핑하지 말아야* 합니다.

Relative IRI (and URL) references *SHOULD NOT* be used within an Activity Streams 2.0 document due to the fact that many JSON parser implementations are not capable of reliably preserving the base context necessary to properly resolve relative references.

상대 IRI(및 URL) 참조는 많은 JSON 파서 구현이 상대 참조를 적절하게 해결하는 데 필요한 기본 컨텍스트를 안정적으로 보존할 수 없기 때문에 Activity Streams 2.0 문서에서는 *사용하지 말아야* 합니다.

## 2.3 [날짜와 시간 (Date and Times)](#2-직렬화-serialization)

All properties with date and time values *MUST* conform to the "date-time" production in [[RFC3339](ActivityStreams2.0Chapter4.md#rfc3339)] with the one exception that seconds *MAY* be omitted. An uppercase "T" character *MUST* be used to separate date and time, and an uppercase "Z" character *MUST* be used in the absence of a numeric time zone offset.

날짜 및 시간 값이 있는 모든 속성은 '초'가 생략 *될 수도* 있는 예외를 제외하고 *반드시* [[RFC3339](ActivityStreams2.0Chapter4.md#rfc3339)]의 "날짜 시간" 생산에 적합해야 합니다. 날짜와 시간을 구분하려면 *반드시* 대문자 "T"를 사용해야 하며 숫자 시간대 오프셋이 없는 경우에는 *반드시* 대문자 "Z"를 사용해야 합니다.

This is specified using the following [[ABNF](ActivityStreams2.0Chapter4.md#abnf)] syntax description. The "time-hour", "time-minute", "time-second", "time-secfrac", "time-offset" and "full-date" constructs are as defined in [ [RFC3339](ActivityStreams2.0ChapterF.md#rfc3339)].

아래 값은 [[ABNF](ActivityStreams2.0Chapter4.md#abnf)] 구문 설명을 사용하여 지정됩니다. "시간 시(time-hour)", "시간 분(time-minute)", "시간 초(time-minute)", "시간 초(time-second)", "시간 분할초(time-secfrac)", "시간 오프셋(time-offset)" 및 "전체 날짜(full-date)" 구성에 대한 정의는 [ [RFC3339](ActivityStreams2.0ChapterF.md#rfc3339)] 에 정의된 바와 같습니다.

```lang-none
as2-partial-time = time-hour ":" time-minute [":" time-second]
                   [time-secfrac]
as2-full-time    = as2-partial-time time-offset
as2-date-time    = full-date "T" as2-full-time
```

It is important to note that the \`time-offset\` component does not correlate to time-zones, and while times that include the \`time-offset\` component work well for timestamps, they cannot be reliably converted to and from local "wall times" without additional information and processing.

\`time-offset\` 구성요소는 시간대과 상관관계가 없으며 \`time-offset\` 구성요소를 포함하는 시간은 타임스탬프에 대해 잘 작동하지만, 추가적인 정보와 처리 없이는 현지의 "정확한 시간" 으로 신뢰성 있게 변환될 수 없다는 점에 유의해야 합니다.

[맨 위로](#2-직렬화-serialization)
