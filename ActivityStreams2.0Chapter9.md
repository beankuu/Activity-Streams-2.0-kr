
## 9. Conformance

All diagrams, examples, and notes in this specification are non-normative, as are all sections explicitly marked non-normative. Everything else in this specification is normative.

### 9.1 Documents

Conforming documents are those that comply with all the conformance criteria for documents. For readability, some of these conformance requirements are phrased as conformance requirements on publishers; such requirements are implicitly requirements on documents: by definition, all documents are assumed to have a publisher.

Conforming documents must not include deprecated or obsolete syntax from Activity Streams 1.0. Conforming documents must include properties and types from the Activity Vocabulary. Conforming documents that use other vocabularies must also include equivalent Activity Vocabulary properties and types as illustrated in Section C. Conforming documents must not use features of JSON-LD or other serialization features disallowed in this specification, as in Section 2. Conforming documents that include types or properties beyond those defined in the Activity Streams 2.0 Vocabulary must use the extensibility features defined in section 5.

A non-exhaustive list of examples of documents includes:

- A document representing an actor
- A document representing an object
- A document representing an activity
- A document representing a collection of the activities done by an actor
- A document representing a collection of the activities done to an object
- A document representing a collection of the activities addressed to an actor or object

### 9.2 Implementations

Conforming implementations are software that publish, store, analyze, consume or otherwise process conforming documents. The two main kinds of implementations are publishers and consumers.

#### 9.2.1 Publishers

Conforming publishers are implementations that create and publish conforming documents. Conforming publishers must make conforming documents available according to the serialization requirements of section 2. Conforming publishers must consider privacy as described in section 6. Conforming publishers must consider security as described in section 7.

A non-exhaustive list of example publishers includes:

- A social network
- A personal web site
- A document publishing system
- A bridge from a non-conforming social network
- A document converter from similar document types such as RSS or Atom

#### 9.2.2 Consumers

Conforming consumers are implementations that read and analyze conforming documents. Conforming consumers must tolerate deprecated or obsolete properties or types from Activity Streams 1.0. Conforming consumers must ignore properties or types that are not applicable to their application domain.

Conforming consumers may re-publish conforming documents in other other data formats. Conforming consumers may present conforming documents to a user on screen, in print, in audio format, or using other presentation mechanisms. Conforming consumers must faithfully translate the information represented in conforming documents into these other formats or media. Conforming consumers that re-publish conforming documents must consider privacy as described in section 6 and security as described in section 7.

A non-exhaustive list of example consumers includes:

- A social network
- A search engine
- A feed reader
- A document validator
- A feed aggregator
- A statistical analyzer
