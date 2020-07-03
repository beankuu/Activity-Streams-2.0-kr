[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 5. Extensibility

In Activity Streams 2.0, an "extension" is any property, activity, actor or object type not defined by the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/). Consuming implementations that encounter unfamiliar extensions *MUST NOT* stop processing or signal an error and *MUST* continue processing the items as if those properties were not present. Note that support for extensions can vary across implementations and no normative processing model for extensions is defined. Accordingly, implementations that rely too heavily on the use of extensions may experience reduced interoperability with other implementations.

For extensions, [[JSON-LD](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD)] is used as the primary mechanism for defining and disambiguating extensions. Implementations that wish to fully support extensions *SHOULD* use [[JSON-LD](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD)] mechanisms.

Some popular extensions are included in the Activity Streams 2.0 namespace document, and can be reviewed at https://www.w3.org/ns/activitystreams#extensions. The [Social Web Incubator Community Group](https://www.w3.org/community/swicg/) maintains a wiki page on [Activity Streams extensions](https://www.w3.org/wiki/Activity_Streams_extensions).

It is important to note that the JSON-LD Processing Algorithms [ [JSON-LD-API](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD-API)], as currently defined, will silently ignore any property not defined in a JSON-LD @context. Implementations that publish Activity Streams 2.0 documents containing extension properties *SHOULD* provide a @context definition for all extensions.

It is also important to note that there are valid JSON constructs which cannot be used within a JSON-LD document. For instance, JSON-LD forbids "arrays of arrays" as used, for example, by the popular [GeoJSON](http://geojson.org/) specification. While implementations are free to use such constructs as extensions within an Activity Streams 2.0 document, consumers that use the standard JSON-LD Processing Algorithms will be required to either ignore such extensions or map those to alternative compatible constructs prior to applying the JSON-LD algorithms. Simple GeoJSON Points, for instance, can be mapped to [Place](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-place) objects, while more complex geometries can be converted to [GeoSparql](http://www.opengeospatial.org/standards/geosparql) "Well-Known Text" representations as illustrated in the non-normative examples below:

<div align="center"><em>
Figure 27 GeoJSON Point Coordinates:
</em></div>

><div align="center"> Example 25 </div>
>
>```json
>{
>  "type": "Point",
>  "coordinates": [36.74, -119.77]
>}
>```

<div align="center"><em>
Figure 28 The Equivalent Place alternative:
</em></div>

><div align="center"> Example 26 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "name": "Fresno, California",
>  "type": "Place",
>  "latitude": 36.74,
>  "longitude": -119.77
>}
>```

<div align="center"><em>
Figure 29 GeoJSON Polygon Coordinates:
</em></div>

><div align="center"> Example 27 </div>
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

><div align="center"> Example 28 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {"gsp": "http://www.opengis.net/ont/geosparql"}
>  ],
>  "summary": "A polygon",
>  "type": "gsp:Geometry",
>  "gsp:asWKT": "Polygon((100.0, 0.0, 101.0, 0.0, 101.0, 1.0, 100.0, 1.0, 100.0, 0.0))"
>}
>```

### 5.1 Support for Compact URIs

The JSON-LD syntax supports the use of "Compact URIs". A "Compact URI" is an alternative encoding of a URI that uses a defined prefix to simplify serialization. For instance, the URI [`http://example.org/term`](http://example.org/term) can be represented as `ex:term` by assigning the `ex:` prefix the value of [`http://example.org/`](http://example.org/)

Within JSON-LD, Compact URI prefixes are defined within the JSON-LD `@context` definition. For example:

<div align="center"><em>
Figure 31 A JSON-LD Compact URI definition
</em></div>

><div align="center"> Example 29 </div>
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

In this example, both the property name `term` and the value `ex:Foo` are Compact URIs. The property name `term` expands to [`http://example.org/term`](http://example.org/term) and the value `ex:Foo` expands to [`http://example.org/Foo`](http://example.org/Foo)

In JSON-LD, Compact URI expansion of values applies to properties explicitly defined as `"type"`: `"id"` in the `@context` definition. Specifically, Compact URIs can be used anywhere an IRI (or URI) value is expected.

Activity Streams 2.0 implementations that wish to fully support extensions *MUST* support Compact URI expansion as defined by the JSON-LD specification. Such expansion applies to all property names as well as all property values explicitly defined as type `@id` in the JSON-LD @context.

Over reliance on the Compact URI form can lead to ambiguity and interoperability issues between implementations. Therefore, Compact URI use *SHOULD* be avoided in all cases other than property names and the value(s) of the `type` property.

### 5.2 Re-serialization of Extensions

Implementations that use JSON-LD mechanisms to parse and then reserialize Activity Streams 2.0 documents that contain extension properties *SHOULD* take sufficient care to ensure that extension properties used within the original document are preserved and serialized appropriately.

For instance, consider the following simple Activity Stream object containing hypothetical `foo` and `bar` extension properties. The `foo` extension is defined within the JSON-LD `@context` while the `bar` extension property is not.

<div align="center"><em>
Figure 32 A simple extended Object
</em></div>

><div align="center"> Example 30 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {"foo": "http://example.org/foo"}
>  ],
>  "type": "Note",
>  "content": "This is a simple note",
>  "foo": 123,
>  "bar": 321
>}
>```

An implementation that receives this Note object can choose to parse the object as an ordinary JSON object or it can use the standard JSON-LD Expansion algorithm.

If the implementation chooses to parse the object as ordinary JSON and then reserializes the object (e.g. for storage or redistribution), then it would simply preserve the values of the `@context`, `foo` and `bar` properties as they are and include those in the reserialized output.

However, if the implementation chooses to use the JSON-LD expansion algorithm, the `@context` will be removed from the expanded result and the `bar` property will be mapped to the "blank node" `_:bar`. If this document is then reserialized using the normative Activity Streams 2.0 context, the JSON-LD compacted form would be:

<div align="center"><em>
Figure 33 The reserialized compacted form:
</em></div>

><div align="center"> Example 31 </div>
>
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "type": "Note",
>  "content": "This is a simple note",
>  "http://example.org/foo": 123,
>  "bar": 321
>}

While this is close to the original, the use of fully expanded URI label for the `foo` property is not ideal. To ensure that the reserialized object is serialized correctly, implementations that perform JSON-LD expansion of received documents *SHOULD* preserve the original `@context` used when performing the JSON-LD expansion, then reuse that when reserializing the object into the JSON-LD compacted form.
