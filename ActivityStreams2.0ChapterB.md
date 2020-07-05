[목차로 돌아가기](ActivityStreams2.0Contents.md)

## B. [사양된 Activity Streams 1.0 문법 (Deprecated Activity Streams 1.0 Syntax)](ActivityStreams2.0Contents.md#목차-table-of-contents)

_This section is non-normative._

_이 항목은 비표준입니다._

Note: While this appendix sections is non-normative, it uses normative terms such as *MUST*. Where used, the meaning is to indicate what would be required to properly implement the Activity Streams 1.0 backwards compatibility model described in this appendix if an implementer chose to do so.

참고: 이 부록 단락은 비-규범적이지만, "*반드시*" 같은 규범적 용어를 사용합니다. 위와 같은 표현이 사용되었다는 것은, 구현자가 부록에 설명된 Activity Streams 1.0 이전 버전과의 호환성 모델을 적절히 구현하기 위해 필요한 사항을 표시하는 것입니다.

While the syntax defined by this specification diverges from that defined by JSON Activity Streams 1.0, the fundamental model defined by that original specification remains intact. Specific processing rules are defined by this specification that allow existing Activity Streams 1.0 documents to be mapped to and processed as an Activity Streams 2.0 document.

이 사양으로 정의된 구문은 JSON Activity Streams 1.0으로 정의된 구문과 다르지만, 원래 사양에 의해 정의된 기본 모델은 그대로 유지됩니다. 이 사양에서는 특정 처리 규격을 정의하여 기존 Activity Streams 1.0 문서를 Activity Streams 2.0 문서로 매핑하고 처리할 수 있습니다.

The JSON syntax defined by this specification differs somewhat from that defined in the original JSON Activity Streams 1.0 [ [AS1](ActivityStreams2.0ChapterF.md#as1)] specification in ways that are not backwards compatible. Implementations can choose to continue supporting the JSON Activity Streams 1.0 syntax but ought consider it to be deprecated. This means that while implementations can continue to consume the 1.0 syntax, they should not output the 1.0 syntax unless specifically interacting with older non-2.0 compliant implementations.

이 사양으로 정의된 JSON 구문은 이전 버전과 호환되지 않는 방식으로 원래 JSON Activity Streams 1.0 [ [AS1](ActivityStreams2.0ChapterF.md#as1)] 사양에서 정의된것과 약간 다릅니다. 구현은 JSON Activity Streams 1.0 구문을 계속 지원하도록 선택할수 있지만, 이 구문은 더이상 사용되지 않는것으로 간주해야 합니다. 즉, 구현에서 1.0 구문을 계속 사용할수 있지만, 2.0이 아닌 이전 구현들과 특별히 상호작용을 하지 않는한 1.0 구문을 출력해서는 안됩니다.

Specifically:

구체적으로는:

[//Comment]: # "5개씩 끊어서"

1. Implementations can use the "`application/stream+json`" MIME media type when producing a JSON serialization using the Activity Streams 1.0 syntax, and "`application/activity+json`" when producing a serialization conforming to the 2.0 syntax.
2. Implementations that process serializations identified using either the "`application/stream+json`" or the more generic "`application/json`" MIME media type *MUST* follow the syntax and processing rules set by [[AS1](ActivityStreams2.0ChapterF.md#as1)]. The 2.0 syntax and processing rules apply only when handling serializations using the "`application/activity+json`" media type.
3. When processing Activity Streams 1.0 documents using a JSON-LD processing model, implementations can use the special AS 1.0 to AS 2.0 expansion @context definition provided [here](https://www.w3.org/ns/activitystreams1-context.jsonld) to produce the JSON-LD expanded representation. Refer to the [JSON-LD Processing Algorithms and API](http://www.w3.org/TR/json-ld-api/#expansion-algorithms) for details.
4. When processing Activity Streams 1.0 documents and converting those to 2.0, implementations ought to treat `id` as an alias for the JSON-LD `@id` key word; and the `objectType` and `verb` properties as aliases for the JSON-LD `@type` keyword.
5. Activity Streams 1.0 uses the `displayName` property which has been renamed to `name` in Activity Streams 2.0. Implementations ought to treat `displayName` as an alias for `name`.

[//Comment]: # "영/한 전환"

1. 구현은  Activity Streams 1.0 구문을 사용하여 JSON 직렬화를 생성할때 "`application/stream+json`" MIME 미디어 타입을 사용할수 있으며, 2.0 구문을 준수하는 직렬화를 생성할때는 "`application/activity+json`" 를 사용할수 있습니다.
2. "`application/stream+json`" 또는 보다 더 일반적인 "`application/json`" MIME 미디어 타입을 사용하여 식별된 직렬화를 처리하는 구현은 *반드시* [[AS1](ActivityStreams2.0ChapterF.md#as1)]에서 설정한 구문 및 처리 규칙을 따라야 합니다. 2.0 구문 및 처리 규칙은 "`application/activity+json`" 미디어 타입을 사용하여 직렬화를 처리할 때만 적용됩니다.
3. JSON-LD 처리 모델을 사용하여 Activity Streams 1.0 문서를 처리할때, 구현에서는 [여기](https://www.w3.org/ns/activitystreams1-context.jsonld)에 제공된 특수 AS 1.0에서 AS2.0으로 확장 @context 정의를 사용하여 JSON-LD 표현을 생성할 수 있습니다. 자세한 내용은 [JSON-LD 처리 알고리즘 및 API](http://www.w3.org/TR/json-ld-api/#expansion-algorithms)를 참조하십시오.
4. Activity Streams 1.0 문서를 처리하고 2.0으로 변환할 때, 구현은 `id`를 JSON-LD `@id` 키워드의 별칭으로 취급해야합니다; JSON-LD `@type` 키워드의 별칭으로는 `objectType`과 `verb` 속성이 있습니다.
5. Activity Streams 1.0은 Activity Streams 2.0에서 `name`으로 변경된 `displayName` 속성을 사용합니다. 구현에서는 `displayName`을 `name`의 별칭으로 취급해야합니다.

[//Comment]: # "5개씩 끊어서"

6. Activity Streams 1.0 uses the `title` property which has been dropped from Activity Streams 2.0. Implementations processing Activity Streams 1.0 documents as Activity Streams 2.0 ought to treat instances of the `title` property as an extension.
7. This document redefines the [content](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content) and [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) properties as natural language values which means their values can be expressed as either a string or an object mapping language tags to string values. In the 1.0 syntax, these are expressed solely as String values. Because the 1.0 values are a valid subset allowed by this specification, implementations are not required to take any specific action to continue supporting those values.
8. This document redefines a large number of common properties defined originally as Objects in 1.0 as either [Objects](https://www.w3.org/TR/activitystreams-core/#asobject) or [Links](https://www.w3.org/TR/activitystreams-core/#dfn-link). The JSON-LD serialization allows such property values to be expressed as either an IRI String, an JSON object, or an Array of IRI Strings and JSON objects. Because the 1.0 values are a valid subset allowed by this specification, existing implementations are not required to take any specific action to continue supporting those values.
9.  This specification deprecates the `upstreamDuplicates` and `downstreamDuplicates` properties defined by Activity Streams 1.0 and does not provide a replacement. This is due largely to lack of any reasonable implementation evidence. While the `upstreamDuplicates` and `downstreamDuplicates` properties *MAY* continue to be used, implementations *SHOULD* avoid them.
10. In Activity Streams 1.0, the "`post`" verb was defined to describe the action of both creating an object and "posting" or uploading it to a service. This specification replaces the "`post`" verb with separate [Create](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-create) and [Add](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-add) Activity types. When processing Activity Streams 1.0 documents and converting those into 2.0, implementations *SHOULD* treat instances of the " `post`" verb as equivalent to [Create](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-create) if there is _no `target` property specified_; and equivalent to [Add](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-add) _if there is a *`target`* property specified_.

[//Comment]: # "영/한 전환"

6. Activity Streams 1.0 은 Activity Streams 2.0 에서 삭제된 `title` 속성을 사용합니다. Activity Streams 2.0 으로 Activity Streams 1.0 문서를 처리하는 구현은 `title` 속성의 인스턴스를 확장인 것으로 처리해야합니다.
7. 이 문서에서는 [content](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-content) 및 [summary](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-summary) 속성을 자연어 값으로 재 정의합니다. 즉, 문자열 값에 언어 태그를 매핑하는 문자열 또는 객체로 표시할수 있습니다. 1.0 구문에서는 문자열 값으로만 표현됩니다. 1.0의 값은 이 스펙에서 허용하는 유효한 하위 집합이므로, 이러한 값을 계속 지원하기 위해 특정한 조치를 취할 필요는 없습니다.
8. 이 문서는 원래 1.0에서 객체(Objects)로 정의된 많은 공통 속성을 [Objects](https://www.w3.org/TR/activitystreams-core/#asobject) 또는 [Links](https://www.w3.org/TR/activitystreams-core/#dfn-link)로 재정의합니다. JSON-LD 직렬화를 통해 이러한 특성값을 IRI 문자열, JSON 객체 또는 IRI 문자열 배열 및 JSON 객체 배열로 표현할수 있습니다. 1.0의 값은 이 스펙에서 허용하는 유효한 하위 집합이므로, 이러한 값을 계속 지원하기 위해 특정한 조치를 취할 필요는 없습니다.
9. 이 사양은 Activity Streams 1.0에 의해 정의된 `upstreamDuplicates` 와 `downstreamDuplicates` 속성을 더 이상 사용하지 않으며 대체제도 제공하지 않습니다. 이는 이를 합리적으로 구현할만한 경우가 적기 떄문입니다. `upstreamDuplicates` 와 `downstreamDuplicates` 속성은 계속 사용될수 있지만, 구현시 이러한 속성은 *피해야 합니다*.
10. Activity Streams 1.0 에서 "`post`" 동사는 객체를 만들고 "posting" 또는 서비스에 업로드하는 동작을 모두 설명하도록 정의되었습니다. 이 사양에서는 "`post`" 동사를 별도의 [Create](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-create) 와 [Add](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-add) 액티비티 타입으로 대체합니다. Activity Streams 1.0 문서를 처리하고 2.0으로 변환할때, 구현시 " `post`" 동사의 인스턴스를 _*`target`* 속성이 없으면_ [Create](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-create), _*`target`* 속성이 있으면_ [Add](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-add) 와 동등한 것으로 *간주해야 합니다*.

By following these guidelines, all JSON Activity Streams 1.0 serializations can be processed successfully by 2.0 implementations.

이 지침을 따르면 2.0구현으로 모든 JSON Activity Streams 1.0 직렬화를 성공적으로 처리할수 있습니다.

[맨 위로](#b-사양된-activity-streams-10-문법-deprecated-activity-streams-10-syntax)
