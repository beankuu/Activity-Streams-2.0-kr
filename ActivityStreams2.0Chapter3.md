[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 3. [예시 (Examples)](ActivityStreams2.0Contents.md#목차-table-of-contents)

_This section is non-normative._

_이 항목은 비표준입니다._

Following are three examples of activities with varying degrees of detail.

다음은 다양한 세부 수준을 가진 액티비티들의 세 가지 예시입니다.

Each example is shown using the normative JSON serialization defined by this specification.

각 예시는 이 사양에서 정의된 표준 JSON 직렬화를 사용하여 표시됩니다.

### 3.1 [최소 액티비티 (Minimal Activity)](#3-예시-examples)

<div align="center"><em>
Figure 4 Expresses the statement <code>'http://www.test.example/martin' created 'http://example.org/foo.jpg'</code>. No additional detail is given.
</em></div>

<div align="center" id="도표-4-httpwwwtestexamplemartin이-httpexampleorgfoojpg를-생성했음을-나타냄-추가-세부사항은-제공되지-않는다"><em>
도표 4 <code>'http://www.test.example/martin'</code>이 <code>'http://example.org/foo.jpg'</code>를 생성했음을 나타냄. 추가 세부사항은 제공되지 않는다.
</em></div>

><div align="center"> Example 4 </div>
>
>```json
>{
>  "summary": "Martin created an image",
>}
>```

><div align="center"> 예시 4 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin은 이미지를 생성했습니다",
>  "type": "Create",
>  "actor": "http://www.test.example/martin",
>  "object": "http://example.org/foo.jpg"
>}
>```

### 3.2 [기본 액티비티 +a (Basic activity with some additional detail)](#3-예시-examples)

<div align="center"><em>
Figure 5 Expresses the statement "Martin Smith added an article to the blog 'Martin's Blog' at 3:04 PM UTC on February 10, 2015." Some additional details about the article, actor and target blog are given using properties defined by the <a href="https://www.w3.org/TR/activitystreams-vocabulary/">Activity Streams 2.0 Vocabulary</a>.
</em></div>

<div align="center" id="도표-5-martin-smith는-2015년-2월-10일-오후-3시-4분-utc에서-martin의-블로그에-글을-추가했다는-문구를-표현-기사-액터-및-대상-블로그에-대한-추가-세부사항은-activity-streams-20-어휘에-의해-정의된-속성을-사용하여-제공된다"><em>
도표 5 "Martin Smith는 2015년 2월 10일 오후 3시 4분 UTC에서 'Martin의 블로그'에 글을 추가했다"는 문구를 표현. 기사, 액터 및 대상 블로그에 대한 추가 세부사항은 <a href="https://www.w3.org/TR/activitystreams-vocabulary/">Activity Streams 2.0 어휘</a>에 의해 정의된 속성을 사용하여 제공된다.
</em></div>


><div align="center"> Example 5 </div>
>
>```json
>{
>  "summary": "Martin added an article to his blog",
>   "name": "Why I love Activity Streams"
>   "name": "Martin's Blog"
>  }
>}
>```

><div align="center"> 예시 5 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin은 자신의 블로그에 글을 올렸습니다",
>  "type": "Add",
>  "published": "2015-02-10T15:04:55Z",
>  "actor": {
>   "type": "Person",
>   "id": "http://www.test.example/martin",
>   "name": "Martin Smith",
>   "url": "http://example.org/martin",
>   "image": {
>     "type": "Link",
>     "href": "http://example.org/martin/image.jpg",
>     "mediaType": "image/jpeg"
>   }
>  },
>  "object" : {
>   "id": "http://www.test.example/blog/abc123/xyz",
>   "type": "Article",
>   "url": "http://example.org/blog/2011/02/entry",
>   "name": "내가 Activity Streams를 사랑하는 이유"
>  },
>  "target" : {
>   "id": "http://example.org/blog/",
>   "type": "OrderedCollection",
>   "name": "Martin의 블로그"
>  }
>}
>```

### 3.3 [확장 액티비티 (An extended activity)](#3-예시-examples)

<div align="center"><em>
Figure 6 A more extensive, single-entry "Activity Stream" follows.
</em></div>

<div align="center" id="도표-6-보다-광범위한-단일-엔트리-activity-stream이-이어짐"><em>
도표 6 보다 광범위한, 단일-엔트리 "Activity Stream"이 이어짐.
</em></div>

><div align="center"> Example 6 </div>
>
>```json
>{
>  "summary": "Martin's recent activities",
>        "name": "My fluffy cat",
>}
>```

><div align="center"> Example 6 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin의 최근 활동",
>  "type": "Collection",
>  "totalItems": 1,
>  "items" : [
>    {
>      "type": "Add",
>      "published": "2011-02-10T15:04:55Z",
>      "generator": "http://example.org/activities-app",
>      "nameMap": {
>        "en": "Martin added a new image to his album.",
>        "ga": "Martin phost le fisean nua a albam."
>      },
>      "actor": {
>        "type": "Person",
>        "id": "http://www.test.example/martin",
>        "name": "Martin Smith",
>        "url": "http://example.org/martin",
>        "image": {
>          "type": "Link",
>          "href": "http://example.org/martin/image",
>          "mediaType": "image/jpeg",
>          "width": 250,
>          "height": 250
>        }
>      },
>      "object" : {
>        "name": "나의 복실복실한 고양이",
>        "type": "Image",
>        "id": "http://example.org/album/máiréad.jpg",
>        "preview": {
>          "type": "Link",
>          "href": "http://example.org/album/máiréad.jpg",
>          "mediaType": "image/jpeg"
>        },
>        "url": [
>          {
>            "type": "Link",
>            "href": "http://example.org/album/máiréad.jpg",
>            "mediaType": "image/jpeg"
>          },
>          {
>            "type": "Link",
>            "href": "http://example.org/album/máiréad.png",
>            "mediaType": "image/png"
>          }
>        ]
>      },
>      "target": {
>        "type": "Collection",
>        "id": "http://example.org/album/",
>        "nameMap": {
>          "en": "Martin's Photo Album",
>          "ga": "Grianghraif Mairtin"
>        },
>        "image": {
>          "type": "Link",
>          "href": "http://example.org/album/thumbnail.jpg",
>          "mediaType": "image/jpeg"
>        }
>      }
>    }
>  ]
>}
>```

[//Comment]: # "nameMap이 en/ga으로 설정되어 있는 부분은 따로 번역을 하지 않겠습니다."

[맨 위로](#3-예시-examples)
