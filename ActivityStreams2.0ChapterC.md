[목차로 돌아가기](ActivityStreams2.0Contents.md)

## C. [복수 어휘들 사용예시 (Example using Multiple Vocabularies)](ActivityStreams2.0Contents.md#목차-table-of-contents)

_This section is non-normative._

_이 항목은 비표준입니다._

It is possible use multiple vocabularies to cover particular characteristics of the activities like data provenance and annotations, which can compliment the Activity Vocabulary. For example: Eric writes a short note to be shared with his followers. After posting the note, he notices a spelling error. He edits the note and re-posts it. Later, Eric decides that the information in the note is incorrect. He deletes the note.

액티비티-어휘를 보완할수 있는 데이터 출저나 주석과 같은 액티비티들의 특정한 특성들을 다루기 위해 여러가지 어휘를 사용할 수 있습니다. 예를 들어: Eric은 그의 팔로워들과 공유할 간단한 노트를 작성합니다. 노트를 게시한 후, 그는 철자 오류를 발견합니다. 그는 메모를 편집하고 다시 게시합니다. 나중에 Eric은 노트의 정보가 올바르지 않다고 판단합니다. 그는 노트를 삭제합니다.

<div align="center"><em>
Figure 34 A series of activities; creating, editing, and deleting a note.
</em></div>

<div align="center" id="도표-34-일련의-활동-노트의-생성-편집과-삭제"><em>
도표 34 일련의 활동; 노트의 생성, 편집과 삭제.
</em></div>

><div align="center"> Example 32 </div>
>
>```json
>{
>  "summary": "Editing history of a note",
>      "summary": "Eric wrote a note.",
>        "content": "Remember... all I'm offering is the trooth. Nothing more.",
>      "summary": "Eric edited a note.",
>        "content": "Remember... all I'm offering is the truth. Nothing more.",
>      "summary": "Eric deleted a note.",
>}
>```

><div align="center"> 예시 32 </div>
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
>  "summary": "노트의 히스토리를 편집",
>  "type": "Collection",
>  "items": [
>    {
>      "id": "http://example.org/activity/20150101000000",
>      "type": [ "Create", "prov:Activity" ],
>      "actor": {
>        "id": "http://example.org/#eric",
>        "name": "Eric"
>      },
>      "summary": "Eric은 노트를 작성했습니다.",
>      "object": {
>        "id": "http://example.org/entry/20150101000000",
>        "type": [ "Note", "prov:Entity" ],
>        "attributedTo": "http://example.org/#eric",
>        "content": "기억해둬... 난 진싦만을 말할 뿐이야. 그게 다야."
>      },
>      "published": "2015-01-01T00:00:00Z"
>    },
>    {
>      "id": "http://example.org/activity/20150101000059",
>      "type": [ "Update", "prov:Activity", "oa:Annotation" ],
>      "summary": "Eric은 노트를 편집했습니다.",
>      "dcterms:created": "2015-01-01T00:00:59Z",
>      "dcterms:creator": { "@id": "http://example.org/#eric" },
>      "oa:hasBody": {
>        "id": "http://example.org/entry/20150101000059",
>        "type": [ "Note", "prov:Entity" ],
>        "content": "기억해둬... 난 진실만을 말할 뿐이야. 그게 다야.",
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
>      "summary": "Eric은 노트를 삭제했습니다.",
>      "object": "http://example.org/entry/20150101000059",
>      "published": "2015-01-01T01:01:01Z"
>    }
>  ]
>}
>```

[맨 위로](#c-복수-어휘들-사용예시-example-using-multiple-vocabularies)
