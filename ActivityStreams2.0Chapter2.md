[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 2. Serialization

This specification describes a JSON-based [[RFC7159](https://www.w3.org/TR/activitystreams-core/#bib-RFC7159)] serialization syntax for the [Activity Vocabulary](https://www.w3.org/TR/activitystreams-vocabulary/) that conforms to a subset of [[JSON-LD](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD)] syntax constraints but does not require JSON-LD processing. While other serialization forms are possible, such alternatives are not discussed by this document.

When serialized, absent properties are represented by either (a) setting the property value to null, or (b) by omitting the property declaration altogether at the option of the publisher. These representations are semantically equivalent. If a property has an array value, the absence of any items in that array MUST be represented by omitting the property entirely or by setting the value to null. The appropriate interpretation of an omitted or explicitly null value is that no value has been assigned as opposed to the view that the given value is empty or nil.

An **Activity Streams Document** is a JSON document whose root value is an Activity Streams [Object](https://www.w3.org/TR/activitystreams-core/#asobject) of any type, including a [Collection](https://www.w3.org/TR/activitystreams-core/#collection), and whose MIME media type is " `application/activity+json`".

Activity Streams 2.0 documents *MUST* be serialized using the UTF-8 character encoding.

### 2.1 JSON-LD

The serialized JSON form of an Activity Streams 2.0 document *MUST* be consistent with what would be produced by the standard JSON-LD 1.0 Processing Algorithms and API [[JSON-LD-API](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD-API)] Compaction Algorithm using, at least, the normative JSON-LD @context definition provided [here](https://www.w3.org/ns/activitystreams). Implementations *MAY* augment the provided @context with additional @context definitions but *MUST NOT* override or change the normative context. Implementations *MAY* also use additional properties and values not defined in the JSON-LD @context with the understanding that any such properties will likely be unsupported and ignored by consuming implementations that use the standard JSON-LD algorithms. See the [Extensibility](https://www.w3.org/TR/activitystreams-core/#extensibility) section for more information on handling extensions within Activity Streams 2.0 documents.

JSON-LD uses the special `@context` property to define the [processing context](http://www.w3.org/TR/json-ld/#the-context). The value of the `@context` property is defined by the [[JSON-LD](https://www.w3.org/TR/activitystreams-core/#bib-JSON-LD)] specification. Implementations producing Activity Streams 2.0 documents *SHOULD* include a `@context` property with a value that includes a reference to the normative [Activity Streams 2.0 JSON-LD @context definition](https://www.w3.org/ns/activitystreams) using the URL " `https://www.w3.org/ns/activitystreams`". Implementations *MAY* use the alternative URL " `http://www.w3.org/ns/activitystreams`" instead. This can be done using a string, object, or array.

### 2.1.1 Context with a string

<div align="center"><em>
Figure 1 Document providing a context as a string.
</em></div>

><div align="center"> Example 1 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "A note",
>  "type": "Note",
>  "content": "My dog has fleas."
>}
>```

### 2.1.2 Context with an object

<div align="center"><em>
Figure 2 Document providing context as an object using the <code>@vocab</code> keyword and a prefix for extension terms.
</em></div>

><div align="center"> Example 2 </div>
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

[//Comment]: # "@language가 en으로 설정되어 있으므로 따로 번역을 하지 않겠습니다."

### 2.1.3 Context with an array

<div align="center"><em>
Figure 3 Document providing context as an array, and including an alias for an additional term.
</em></div>

><div align="center"> Example 3 </div>
>
>```json
>{
>  "@context": [
>     "https://www.w3.org/ns/activitystreams",
>     {
>      "css": "http://www.w3.org/ns/oa#styledBy"
>     }
>  ],
>  "summary": "A note",
>  "type": "Note",
>  "content": "My dog has fleas.",
>  "css": "http://www.csszengarden.com/217/217.css?v=8may2013"
>}
>```

When a JSON-LD enabled Activity Streams 2.0 implementation encounters a JSON document identified using the " `application/activity+json`" MIME media type, and that document does not contain a `@context` property whose value includes a reference to the normative [Activity Streams 2.0 JSON-LD @context definition](https://www.w3.org/ns/activitystreams), the implementation *MUST* assume that the normative @context definition still applies.

### 2.2 IRIs and URLs

This specification uses IRIs [[RFC3987](https://www.w3.org/TR/activitystreams-core/#bib-RFC3987)]. Every URI [[RFC3986](https://www.w3.org/TR/activitystreams-core/#bib-RFC3986)] is also an IRI, so a URI may be used wherever an IRI is named. There are two special considerations: (1) when an IRI that is not also a URI is given for dereferencing, it *MUST* be mapped to a URI using the steps in Section 3.1 of [[RFC3987](https://www.w3.org/TR/activitystreams-core/#bib-RFC3987)] and (2) when an IRI is serving as an "id" value, it *MUST NOT* be so mapped.

Relative IRI (and URL) references *SHOULD NOT* be used within an Activity Streams 2.0 document due to the fact that many JSON parser implementations are not capable of reliably preserving the base context necessary to properly resolve relative references.
2.3 Date and Times

All properties with date and time values *MUST* conform to the "date-time" production in [[RFC3339](https://www.w3.org/TR/activitystreams-core/#bib-RFC3339)] with the one exception that seconds *MAY* be omitted. An uppercase "T" character *MUST* be used to separate date and time, and an uppercase "Z" character *MUST* be used in the absence of a numeric time zone offset.

This is specified using the following [[ABNF](https://www.w3.org/TR/activitystreams-core/#bib-ABNF)] syntax description. The "time-hour", "time-minute", "time-second", "time-secfrac", "time-offset" and "full-date" constructs are as defined in [ [RFC3339](https://www.w3.org/TR/activitystreams-core/#bib-RFC3339)].

```
as2-partial-time = time-hour `":"` time-minute [`":"` time-second]
                   [time-secfrac]
as2-full-time    = as2-partial-time time-offset
as2-date-time    = full-date `"T"` as2-full-time
```

It is important to note that the \`time-offset\` component does not correlate to time-zones, and while times that include the \`time-offset\` component work well for timestamps, they cannot be reliably converted to and from local "wall times" without additional information and processing.
