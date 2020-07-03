[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 3. Examples

_This section is non-normative._

Following are three examples of activities with varying degrees of detail.

Each example is shown using the normative JSON serialization defined by this specification.

### 3.1 Minimal Activity

<div align="center"><em>
Figure 4 Expresses the statement <code>'http://www.test.example/martin' created 'http://example.org/foo.jpg'</code>. No additional detail is given.
</em></div>

><div align="center"> Example 4 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin created an image",
>  "type": "Create",
>  "actor": "http://www.test.example/martin",
>  "object": "http://example.org/foo.jpg"
>}
>```

### 3.2 Basic activity with some additional detail

<div align="center"><em>
Figure 5 Expresses the statement "Martin Smith added an article to the blog 'Martin's Blog' at 3:04 PM UTC on February 10, 2015." Some additional details about the article, actor and target blog are given using properties defined by the <a href="https://www.w3.org/TR/activitystreams-vocabulary/">Activity Streams 2.0 Vocabulary</a>.
</em></div>

><div align="center"> Example 5 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin added an article to his blog",
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
>   "name": "Why I love Activity Streams"
>  },
>  "target" : {
>   "id": "http://example.org/blog/",
>   "type": "OrderedCollection",
>   "name": "Martin's Blog"
>  }
>}
>```

### 3.3 An extended activity

<div align="center"><em>
Figure 6 A more extensive, single-entry "Activity Stream" follows.
</em></div>

><div align="center"> Example 6 </div>
>
>```json
>{
>  "@context": "https://www.w3.org/ns/activitystreams",
>  "summary": "Martin's recent activities",
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
>        "name": "My fluffy cat",
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
