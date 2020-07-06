[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 5. [확장성 (Extensibility)](ActivityStreams2.0Contents.md#목차-table-of-contents)

In Activity Streams 2.0, an "extension" is any property, activity, actor or object type not defined by the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/). Consuming implementations that encounter unfamiliar extensions *MUST NOT* stop processing or signal an error and *MUST* continue processing the items as if those properties were not present. Note that support for extensions can vary across implementations and no normative processing model for extensions is defined. Accordingly, implementations that rely too heavily on the use of extensions may experience reduced interoperability with other implementations.

Activity Streams 2.0 에서 "확장"은 [Acvitity 어휘](https://www.w3.org/TR/activitystreams-vocabulary/)에 의해 정의되지 않은 모든 속성, 액티비티, 액터 또는 객체 유형입니다. 익숙하지 않은 확장을 포함한 구현을 처리할 경우 처리를 중지하거나 오류를 표시해서는 *절대 안되며*, *반드시* 해당 속성이 없는것처럼 항목을 계속 처리해야합니다. 확장에 대한 지원은 구현마다 다를수 있으며 확장에 대한 처리 모델 규정은 정의되어 있지 않습니다. 따라서, 확장의 사용에 너무 의존하는 구현은 다른 구현과의 상호 운용성이 저하될 수 있습니다.

For extensions, [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] is used as the primary mechanism for defining and disambiguating extensions. Implementations that wish to fully support extensions *SHOULD* use [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] mechanisms.

확장의 경우, [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)]가 확장을 정의 및 구분하는 기본 메커니즘으로 사용됩니다. 확장을 완전히 지원하려는 구현에서는 [[JSON-LD](ActivityStreams2.0ChapterF.md#json-ld)] 메커니즘을 *사용해야 합니다*.

Some popular extensions are included in the Activity Streams 2.0 namespace document, and can be reviewed at https://www.w3.org/ns/activitystreams#extensions. The [Social Web Incubator Community Group](https://www.w3.org/community/swicg/) maintains a wiki page on [Activity Streams extensions](https://www.w3.org/wiki/Activity_Streams_extensions).

자주 사용되는 일부 확장명은 Activity Streams 2.0 네임스페이스 문서에 포함되어 있으며 https://www.w3.org/ns/activitystreams#extensions 에서 검토할 수 있습니다. [Social Web Incubator Community Group](https://www.w3.org/community/swicg/) 은 [Activity Streams 확장](https://www.w3.org/wiki/Activity_Streams_extensions) 에 대한 위키 페이지를 유지합니다.

It is important to note that the JSON-LD Processing Algorithms [ [JSON-LD-API](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD-API)], as currently defined, will silently ignore any property not defined in a JSON-LD @context. Implementations that publish Activity Streams 2.0 documents containing extension properties *SHOULD* provide a @context definition for all extensions.

현재 정의된 JSON-LD 처리 알고리즘인 [ [JSON-LD-API](ActivityStreams2.0ChapterF.md#json-ld-api)] 는 JSON-LD @context에 정의되지 않은 속성을 자동으로 무시합니다. 확장 속성을 포함하는 Activity Streams 2.0 문서를 게시하는 구현에서는 모든 확장에 대해 @context 정의를 *제공해야 합니다*.

It is also important to note that there are valid JSON constructs which cannot be used within a JSON-LD document. For instance, JSON-LD forbids "arrays of arrays" as used, for example, by the popular [GeoJSON](http://geojson.org/) specification. While implementations are free to use such constructs as extensions within an Activity Streams 2.0 document, consumers that use the standard JSON-LD Processing Algorithms will be required to either ignore such extensions or map those to alternative compatible constructs prior to applying the JSON-LD algorithms. Simple GeoJSON Points, for instance, can be mapped to [Place](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-place) objects, while more complex geometries can be converted to [GeoSparql](http://www.opengeospatial.org/standards/geosparql) "Well-Known Text" representations as illustrated in the non-normative examples below:

또한 JSON-LD 문서 내에서 사용할수 없는 유효한 JSON 구조가 있습니다. 예를 들어, JSON-LD는 널리 사용되는 [GeoJSON](http://geojson.org/) 규격에 사용되는 "배열의 배열"을 금지합니다. 구현시 Activity Streams 2.0 문서에서 이러한 구성을 확장으로는 자유롭게 사용할 수 있지만, 표준 JSON-LD 처리 알고리즘을 사용하는 소비자는 JSON-LD 알고리즘을 적용하기 전에 이러한 확장을 무시하거나 호환 가능한 다른 구성에 매핑해야 합니다. 예를 들어, 단순 GeoJSON 점 을 [Place](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-place) 객체에 매핑할 수 있으며, 보다 복잡한 지오메트리를 아래의 비정규 예시에서와 같이 [GeoSparql](http://www.opengeospatial.org/standards/geosparql)의 "잘 알려진 텍스트" 표현으로 변환할 수 있습니다.

<div align="center"><em>
Figure 27 GeoJSON Point Coordinates:
</em></div>

<div align="center" id="도표-27-geojson-점point-좌표"><em>
도표 27 GeoJSON 점(Point) 좌표:
</em></div>

><div align="center"> Example 25 </div>

><div align="center"> 예시 25 </div>
>
>```json
>{
>  "type": "Point",
>  "coordinates": [36.74, -119.77]
>}
>```

<div align="center"><em>
Figure 28 The Equivalent <code>Place</code> alternative:
</em></div>

<div align="center" id="도표-28-place와-동등한-대안"><em>
도표 28 <code>Place</code>와 동등한 대안:
</em></div>

><div align="center"> Example 26 </div>
>
>```json
>{
>  "name": "Fresno, California",
>}
>```

><div align="center"> 예시 26 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "name": "프레즈노, 캘리포니아",
>  "type": "Place",
>  "latitude": 36.74,
>  "longitude": -119.77
>}
>```

<div align="center"><em>
Figure 29 GeoJSON Polygon Coordinates:
</em></div>

<div align="center" id="도표-29-geojson-다각형-좌표들"><em>
도표 29 GeoJSON 다각형 좌표들:
</em></div>

><div align="center"> Example 27 </div>

><div align="center"> 예시 27 </div>
>
>```json
>{
>  "type": "Polygon",
>  "coordinates": [
>    [
>      [100.0, 0.0],
>      [101.0, 0.0],
>      [101.0, 1.0],
>      [100.0, 1.0],
>      [100.0, 0.0]
>    ]
>  ]
>}
>```

<div align="center"><em>
Figure 30 The Equivalent GeoSparql Well-Known-Text alternative:
</em></div>

<div align="center" id="도표-30-잘-알려진-geosparql과-동등한-대안"><em>
도표 30 잘 알려진 GeoSparql과 동등한 대안:
</em></div>

><div align="center"> Example 28 </div>
>
>```json
>{
>  "summary": "A polygon",
>}
>```

><div align="center"> 예시 28 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {"gsp": "http://www.opengis.net/ont/geosparql"}
>  ],
>  "summary": "다각형",
>  "type": "gsp:Geometry",
>  "gsp:asWKT": "Polygon((100.0, 0.0, 101.0, 0.0, 101.0, 1.0, 100.0, 1.0, 100.0, 0.0))"
>}
>```

### 5.1 [단축 URI 지원 (Support for Compact URIs)](#5-확장성-extensibility)

The JSON-LD syntax supports the use of "Compact URIs". A "Compact URI" is an alternative encoding of a URI that uses a defined prefix to simplify serialization. For instance, the URI `http://example.org/term` can be represented as `ex:term` by assigning the `ex:` prefix the value of `http://example.org/`

JSON-LD 구문은 "단축 URI" 사용을 지원합니다. "단축 URI"는 사전에 정의된 접두사를 사용하여 직렬화를 단순화하는 URI의 대체 인코딩입니다. 예를 들어, URI `http://example.org/term`은 `ex:` 접두사 값으로 `http://example.org/` 를 할당하면 `ex:term` 처럼 표기할수 있습니다.

Within JSON-LD, Compact URI prefixes are defined within the JSON-LD `@context` definition. For example:

JSON-LD 내에서 단축 URI 접두사는 JSON-LD `@context` 정의 내에 정의됩니다. 예를 들어 :

<div align="center"><em>
Figure 31 A JSON-LD Compact URI definition
</em></div>

<div align="center" id="도표-31-json-ld-압축-uri-정의"><em>
도표 31 JSON-LD 압축 URI 정의
</em></div>

><div align="center"> Example 29 </div>

><div align="center"> 예시 29 </div>
>
>```json
>{
>"@context": {
>"ex": "http://example.org/",
>"term": {
>  "@type": "id",
>  "@id": "ex:term"
>}
>},
>"term": "ex:Foo"
>}
>```

In this example, both the property name `term` and the value `ex:Foo` are Compact URIs. The property name `term` expands to `http://example.org/term` and the value `ex:Foo` expands to `http://example.org/Foo`

이 예시에서는 속성 이름 `term`과 값 `ex:Foo` 모두 단축 URI입니다. 속성 이름 `term`은 `http://example.org/term` 으로 확장되고, 값 `ex:Foo`는 `http://example.org/Foo`로 확장됩니다.

In JSON-LD, Compact URI expansion of values applies to properties explicitly defined as `"type"`: `"id"` in the `@context` definition. Specifically, Compact URIs can be used anywhere an IRI (or URI) value is expected.

JSON-LD에서 값의 단축 URI 확장은 `@context` 정이에서의 `"type"`: `"id"` 로 명시적으로 정의된 속성에 적용됩니다. 특히 IRI(또는 URI)값이 예상되는 모든 곳에서 단축 URI를 사용할수 있습니다.

Activity Streams 2.0 implementations that wish to fully support extensions *MUST* support Compact URI expansion as defined by the JSON-LD specification. Such expansion applies to all property names as well as all property values explicitly defined as type `@id` in the JSON-LD @context.

확장을 완전히 지원하는 Activity Streams 2.0 구현은 *반드시* JSON-LD 규격에 정의된 단축 URI 확장을 지원해야 합니다. 이러한 확장은 JSON-LD @context 내에서 `@id` 타입으로 명시적으로 정의된 모든 속성 값 뿐만아니라 모든 속성 이름에 적용됩니다.

Over reliance on the Compact URI form can lead to ambiguity and interoperability issues between implementations. Therefore, Compact URI use *SHOULD* be avoided in all cases other than property names and the value(s) of the `type` property.

단축 URI 양식에 지나치게 의존하면 구현간 모호성 및 상호 운용성 문제가 발생할 수 있습니다. 따라서 속성 이름 및 `type` 속성의 값을 제외한 모든 경우에는 단축 URI 사용을 회피 *해야 합니다*.

### 5.2 [확장의 재-직렬화 (Re-serialization of Extensions)](#5-확장성-extensibility)

Implementations that use JSON-LD mechanisms to parse and then reserialize Activity Streams 2.0 documents that contain extension properties *SHOULD* take sufficient care to ensure that extension properties used within the original document are preserved and serialized appropriately.

JSON-LD 메커니즘을 사용하여 확장 속성을 포함하는 Activity Streams 2.0 문서를 구문 분석 및 재-직렬화 하는 구현은 원본 문서 내에서 사용된 확장 속성이 적절히 보존되고 직렬화하도록 충분히 주의 *해야 합니다*.

For instance, consider the following simple Activity Stream object containing hypothetical `foo` and `bar` extension properties. The `foo` extension is defined within the JSON-LD `@context` while the `bar` extension property is not.

예를 들어, 가상의 `foo`와 `bar` 확장 속성이 포함된 다음과 같은 Activity Stream 객체를 고려합니다. `foo` 확장자는 JSON-LD `@context` 내에서 정의되지만 `bar` 확장 속성은 정의되지 않습니다.

<div align="center"><em>
Figure 32 A simple extended Object
</em></div>

<div align="center" id="도표-32-간단한-확장된-객체"><em>
도표 32 간단한 확장된 객체
</em></div>

><div align="center"> Example 30 </div>
>
>```json
>{
>  "content": "This is a simple note",
>}
>```

><div align="center"> 예시 30 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {"foo": "http://example.org/foo"}
>  ],
>  "type": "Note",
>  "content": "이것은 간단한 노트입니다",
>  "foo": 123,
>  "bar": 321
>}
>```

An implementation that receives this Note object can choose to parse the object as an ordinary JSON object or it can use the standard JSON-LD Expansion algorithm.

이 노트 객체를 수신하는 구현에서는 객체를 일반 JSON 객체로 취급하여 구문을 분석하거나 표준 JSON-LD 확장 알고리즘을 사용하여 구문 분석을 할수 있습니다.

If the implementation chooses to parse the object as ordinary JSON and then reserializes the object (e.g. for storage or redistribution), then it would simply preserve the values of the `@context`, `foo` and `bar` properties as they are and include those in the reserialized output.

구현이 객체를 일반 JSON으로 구문 분석하여 객체를 재-직렬화(예: 저장 또는 재배포) 하는 경우에는 단순히 `@context`, `foo`와 `bar` 속성의 값을 그대로 보존하고 재-직렬화된 출력에 포함시킵니다.

However, if the implementation chooses to use the JSON-LD expansion algorithm, the `@context` will be removed from the expanded result and the `bar` property will be mapped to the "blank node" `_:bar`. If this document is then reserialized using the normative Activity Streams 2.0 context, the JSON-LD compacted form would be:

한편, 이 구현에서 JSON-LD 확장 알고리즘을 사용하기로 선택하면 확장된 결과에서는 `@context`가 제거되고 `bar` 속성이 "비어있는 노드" `_:bar`에 매핑됩니다. 이 문서가 Activity Streams 2.0 컨텍스트를 사용하여 재-직렬화될 경우의 JSON-LD 단축 양식은 다음과 같습니다:

<div align="center"><em>
Figure 33 The reserialized compacted form:
</em></div>

<div align="center" id="도표-33-재-직렬화된-압축된-형식"><em>
도표 33 재-직렬화된 압축된 형식:
</em></div>

><div align="center"> Example 31 </div>
>
>```json
>{
>  "content": "This is a simple note",
>}
>```

><div align="center"> 예시 31 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Note",
>  "content": "이것은 간단한 노트입니다",
>  "http://example.org/foo": 123,
>  "bar": 321
>}
>```

While this is close to the original, the use of fully expanded URI label for the `foo` property is not ideal. To ensure that the reserialized object is serialized correctly, implementations that perform JSON-LD expansion of received documents *SHOULD* preserve the original `@context` used when performing the JSON-LD expansion, then reuse that when reserializing the object into the JSON-LD compacted form.

이는 원본에 가깝지만, `foo` 속성에 대해 완전하게 확장된 URI 레이블을 사용하는 것은 이상적이지 않습니다. 재-직렬화 객체가 올바르게 직렬화되는것을 보장하려면, 수신받은 문서의 JSON-LD 확장을 수행하는 구현에서 JSON-LD 확장을 수행할때, 일단 사용된 원래의 `@context`를 보존한 후, 객체를 다시 JSON-LD 단축 양식으로 재-직렬화를 할때 이를 재사용 *해야 합니다*.

[맨 위로](#5-확장성-extensibility)
