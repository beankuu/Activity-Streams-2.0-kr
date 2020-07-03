[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 1. Introduction

In the most basic sense, an "Activity" is a semantic description of an action. It is the goal of this specification to provide a JSON-based syntax that is sufficient to express metadata about activities in a rich, human-friendly but machine-processable and extensible manner. This can include constructing natural-language descriptions or visual representations about the activity, associating actionable information with various types of objects, communicating or recording activity logs, or delegation of potential actions to other applications.

The key words "*MUST*", "*MUST NOT*", "*REQUIRED*", "*SHALL*", "*SHALL NOT*", " *SHOULD*", "*SHOULD NOT*", "*RECOMMENDED*", "*MAY*", and "*OPTIONAL*" in this document are to be interpreted as described in [[RFC2119](https://www.w3.org/TR/activitystreams-core/#bib-RFC2119)].

### 1.1 Relationship to Other Social Standards

_This section is non-normative._

Activity Streams 2.0 is suitable as a social data syntax. It forms part of the [[SWP](https://www.w3.org/TR/activitystreams-core/#bib-SWP)] suite of related standards.

### 1.2 Relationship to JSON Activity Streams 1.0

_This section is non-normative._

The JSON Activity Streams 1.0 [[AS1](https://www.w3.org/TR/activitystreams-core/#bib-AS1)] specification was published in May of 2011 and provided a baseline extensible syntax for the expression of completed activities. This specification builds upon that initial foundation by incorporating lessons learned through extensive implementation, community feedback and related ongoing work from a variety of other communities.

Some of the issues that specifically motivated the evolution of Activity Streams 2.0 from Activity Streams 1.0 include:

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

The terms `displayName`, `verb`, `title` and `objectType` should be treated as reserved terms that *SHOULD NOT* be used within Activity Streams 2.0 documents. When encountered in an Activity Streams 2.0 document, they SHOULD be processed in accordance to the guidelines listed in [B. Deprecated Activity Streams 1.0 Syntax](https://www.w3.org/TR/activitystreams-core/#activitystreams-1.0a)
