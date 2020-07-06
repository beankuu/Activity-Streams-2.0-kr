[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 8. [IANA 고려사항 (IANA Considerations)](ActivityStreams2.0Contents.md#목차-table-of-contents)

### 8.1 [`application/activity+json` 미디어 타입 (The `application/activity+json` Media Type)](#8-iana-고려사항-iana-considerations)

This specification registers the `application/activity+json` MIME Media Type specifically for identifying documents conforming to the Activity Streams 2.0 format.

이 사양은 Activity Streams 2.0 규격을 따르는 문서를 식별하기 위해 `application/activity+json` 미디어 유형을 등록합니다.

.| |
---|---
Type name: | application
Subtype name: | activity+json
Required parameters: | None
Optional parameters: | profile: The profile parameter for the application/activity+json media type allows one or more profile URIs to be specified. These profile URIs have the identifier semantics defined in [[RFC6906](ActivityStreams2.0ChapterF.md#rfc6906)]. The "profile" media type parameter *MUST* be quoted. It contains a non-empty list of space-separated URIs (the profile URIs). </br></br> profile-param = <code>"profile="</code> profile-value </br> profile-value = <"> profile-URI 0*( 1*SP profile-URI ) <"> </br> profile-URI   = URI </br></br> The "URI" in the above grammar refers to the "URI" as defined in Section 3 of [[RFC3986](ActivityStreams2.0ChapterF.md#rfc3986)].
Encoding considerations: | Resources that use the "`application/activity+json`" Media Type are required to conform to all of the requirements for the "`application/json`" Media Type and are therefore subject to the same encoding considerations specified in Section 11 of [[RFC7159](ActivityStreams2.0ChapterF.md#rfc3986)].
Security considerations: | As defined in this specification.
Contact:  | James M Snell <jasnell@gmail.com>

.| |
---|---
타입 이름: | application
하위 타입 이름: | activity+json
필수 매개변수: | 없음
선택적 매개변수: | profile: 프로필(profile) application/activity+json 미디어 타입의 profile 매개변수를 사용하면 하나 이상의 profile URI를 지정할 수 있습니다. 이러한 profile URI에는 [[RFC6906](ActivityStreams2.0ChapterF.md#rfc6906)]에 정의된 식별자 도안이 있습니다. "profile" 미디어 타입 매개변수는 *반드시* 따옴표로 묶어야 합니다. 공백으로 구분한 URI(profile URI)들의 비어있지 않은 목록을 포함하고 있습니다. </br></br> profile-param = <code>"profile="</code> profile-value </br> profile-value = <"> profile-URI 0*( 1*SP profile-URI ) <"> </br> profile-URI   = URI </br></br> 위의 문법에서의 "URI"는 [[RFC3986](ActivityStreams2.0ChapterF.md#rfc3986)]의 섹션 3에 정의된 "URI"를 뜻합니다.
인코딩 고려사항: | "`application/activity+json`" 미디어 타입을 사용하는 리소스는 "`application/json`" 미디어 타입에 대한 모든 요구사항을 준수해야 하므로 [[RFC7159](ActivityStreams2.0ChapterF.md#rfc3986)]의 섹션 11에 명시된 것과 동일한 인코딩 고려 사항이 적용됩니다.
보안 고려사항: | 이 문서에 등록된 사양을 따릅니다
연락처:  | James M Snell <jasnell@gmail.com>

Note that while the Activity Streams 2.0 format uses JSON-LD conventions, there are a number of constraints and additional requirements for Activity Streams 2.0 implementations that justify the use of a specific media type.

Activity Streams 2.0 규격은 JSON-LD 규칙을 사용하지만, 특정 미디어 유형의 사용을 정당화하는 Activity Streams 2.0 구현에는 여러 제약 조건과 추가적인 요구사항둘이 있습니다.

Because Activity Streams 2.0 can be considered a restricted profile of JSON-LD, Implementations *SHOULD* consider the \`application/ld+json; profile="https://www.w3.org/ns/activitystreams"\` media type as being equivalent to \`application/activity+json\`.

Activity Streams 2.0은 JSON-LD의 제한된 프로필로 간주될수 있으므로, 구현에서는 \`application/ld+json; profile="https://www.w3.org/ns/activitystreams"\` 미디어 유형을 \`application/activity+json\` 과 동등하다고 간주해야 합니다.

[맨 위로](#8-iana-고려사항-iana-considerations)
