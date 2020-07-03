[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 8. IANA Considerations

### 8.1 The `application/activity+json` Media Type

This specification registers the `application/activity+json` MIME Media Type specifically for identifying documents conforming to the Activity Streams 2.0 format.

.| |
---|---
Type name: | application
Subtype name: | activity+json
Required parameters: | None
Optional parameters: | profile: The profile parameter for the application/activity+json media type allows one or more profile URIs to be specified. These profile URIs have the identifier semantics defined in [[RFC6906](https://www.w3.org/TR/activitystreams-core/#bib-RFC6906)]. The "profile" media type parameter *MUST* be quoted. It contains a non-empty list of space-separated URIs (the profile URIs). </br> * profile-param = <code>"profile="</code> profile-value </br> profile-value = <"> profile-URI 0*( 1*SP profile-URI ) <"> </br> * profile-URI   = URI </br> The "URI" in the above grammar refers to the "URI" as defined in Section 3 of [[RFC3986](https://www.w3.org/TR/activitystreams-core/#bib-RFC3986)].
Encoding considerations: | Resources that use the "`application/activity+json`" Media Type are required to conform to all of the requirements for the "`application/json`" Media Type and are therefore subject to the same encoding considerations specified in Section 11 of [[RFC7159](https://www.w3.org/TR/activitystreams-core/#bib-RFC3986)].
Security considerations: | As defined in this specification.
Contact:  | James M Snell <jasnell@gmail.com>

Note that while the Activity Streams 2.0 format uses JSON-LD conventions, there are a number of constraints and additional requirements for Activity Streams 2.0 implementations that justify the use of a specific media type.

Because Activity Streams 2.0 can be considered a restricted profile of JSON-LD, Implementations *SHOULD* consider the \`application/ld+json; profile="https://www.w3.org/ns/activitystreams"\` media type as being equivalent to \`application/activity+json\`.
