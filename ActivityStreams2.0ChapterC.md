[목차로 돌아가기](ActivityStreams2.0Contents.md)

## C. Example using Multiple Vocabularies

_This section is non-normative._

It is possible use multiple vocabularies to cover particular characteristics of the activities like data provenance and annotations, which can compliment the Activity Vocabulary. For example: Eric writes a short note to be shared with his followers. After posting the note, he notices a spelling error. He edits the note and re-posts it. Later, Eric decides that the information in the note is incorrect. He deletes the note.

<div align="center"><em>
Figure 34 A series of activities; creating, editing, and deleting a note.
</em></div>

><div align="center"> Example 32 </div>
>
>```json
>{
>  "@context": [
>    "https://www.w3.org/ns/activitystreams",
>    {
>      "oa": "http://www.w3.org/ns/oa#",
>      "prov": "http://www.w3.org/ns/prov#",
>      "dcterms": "http://purl.org/dc/terms/",
>      "dcterms:created": {
>        "@id": "dcterms:created",
>        "@type": "xsd:dateTime"
>      }
>    }
>  ],
>  "summary": "Editing history of a note",
>  "type": "Collection",
>  "items": [
>    {
>      "id": "http://example.org/activity/20150101000000",
>      "type": [ "Create", "prov:Activity" ],
>      "actor": {
>        "id": "http://example.org/#eric",
>        "name": "Eric"
>      },
>      "summary": "Eric wrote a note.",
>      "object": {
>        "id": "http://example.org/entry/20150101000000",
>        "type": [ "Note", "prov:Entity" ],
>        "attributedTo": "http://example.org/#eric",
>        "content": "Remember... all I'm offering is the trooth. Nothing more."
>      },
>      "published": "2015-01-01T00:00:00Z"
>    },
>    {
>      "id": "http://example.org/activity/20150101000059",
>      "type": [ "Update", "prov:Activity", "oa:Annotation" ],
>      "summary": "Eric edited a note.",
>      "dcterms:created": "2015-01-01T00:00:59Z",
>      "dcterms:creator": { "@id": "http://example.org/#eric" },
>      "oa:hasBody": {
>        "id": "http://example.org/entry/20150101000059",
>        "type": [ "Note", "prov:Entity" ],
>        "content": "Remember... all I'm offering is the truth. Nothing more.",
>        "prov:wasAttributedTo": { "@id": "http://example.org/#eric" },
>        "prov:wasRevisionOf": { "@id": "http://example.org/entry/20150101000000" }
>      },
>      "oa:hasTarget": { "@id": "http://example.org/entry/20150101000000" },
>      "oa:motivatedBy": { "@id": "oa:editing" },
>      "prov:generated": { "@id": "http://example.org/entry/20150101000059" },
>      "prov:wasInformedBy": { "@id": "http://example.org/activity/20150101000000" }
>    },
>    {
>      "id": "http://example.org/activity/20150101010101",
>      "type": [ "Delete", "prov:Activity" ],
>      "actor": "http://example.org/#eric",
>      "summary": "Eric deleted a note.",
>      "object": "http://example.org/entry/20150101000059",
>      "published": "2015-01-01T01:01:01Z"
>    }
>  ]
>}
>```
