[README로 돌아가기](README.md)

# ActivityStreams2.0 문서 한글 번역 가이드라인

- 임시로 작성한 문서입니다.
- ActivityPub / ActivityStreams2.0 번역 가이드라인들과 내용이 유사합니다.

## 1. 번역 단어관련

- 번역하면서 자주 등장하고 오역이 흔했던 단어들 위주로 작성하였습니다.

### 1.1 단어 전체를 번역

원문 | 번역 | 비고
-- | -- | --
specification | 사양 / 규격
Publisher | 출판자 / 게시자
type | 유형 | 1.2 음차로도 번역
application | 어플리케이션
conformance | 준수 / 규정
normative | 규범적인
form | 양식 / 형식
format | 규격 / 양식 / 형식

### 1.2 음차를 사용하는 번역

원문 | 번역 | 비고
-- | -- | --
section | 섹션
use case | 유즈케이스
geometry | 지오메트리
syntax | 신택스
type | 타입 | 1.1 단어 전체로도 번역
collection | 컬렉션
paging | 페이징
Media type | 미디어 타입

### 1.3 원문 그대로 사용하는 번역

원문 | 비고
-- | --
Activity Streams |
Social Web Incubator Community Group |
Social Web Community Group |

### 1.4 원문과 번역본을 혼용해 사용하는 번역

원문 | 번역 |  비고
-- | -- | --
subtype | 하위 타입
Activity Vocabulary | Activity 어휘
Activity data | Activity 데이터

## 2. 번역 일관성

### 2.1 RFC2119

> 본문에서 RFC2119에 대한 내용은 Chapter1에 기재되어 있습니다.

원문 | 번역 예 | 키워드
-- | -- | --
A `CAN` B C | A는 C에게 `B 수` 있습니다 | `수`
A `MAY` B C | A는 C에게 `B 수도` 있습니다 | `수도`
A `SHOULD` B C | A는 C에게 `B 합니다` | -
A `SHOULD NOT` B C | A는 C에게 `B 말아야` 합니다 | `말아야`
A `MUST` B C | A는 C에게 `반드시` B 합니다 | `반드시`
A `MUST NOT` B C | A는 C에게 `절대 B` 안 됩니다 | `절대`
A `SHALL` B C | A는 C에게 `할 것` 입니다 | `것`
A `SHALL NOT` B C | A는 C에게 `B 말아야 할 것` 입니다 | `말아야 할 것`
A `RECOMMENDED` to B C | A는 C에게 B `권장합니다` | `권장`
A is `OPTIONAL` to B C | A는 C에게 B 위해서의 `선택사항` 입니다 | `선택`
A is `REQUIRED` to B C | A는 C에게 B 위해서 `필요합니다` | `필요`

## 3. markdown 등 그 외 관련

@ [종합본](ActivityVocabulary.md)에서는 다음과 같은 양식을 사용했습니다 :

```language-none
번역본
```

@ 개별 챕터 번역본에서는 다음과 같은 양식을 사용했습니다 :

```language-none
원문
번역본
주석
```

@ 예시에서는 다음과 같은 양식을 사용했습니다 :

> 예시 N번
>
>```json
>{
>   "name": "번역할 문장만"
>}
>```

@ `[WORD](LINK)`

- WORD
  - {번역한 단어}를 사용하되, 의미전달이 애매할 경우는 {번역(원문)}
- LINK
  - 개별 파일에서는 원문 링크를 따르기
    - 예: `[Extensibility](https://www.w3.org/TR/activitystreams-core/#extensibility)`
  - [종합본](ActivityVocabulary.md)에는 최대한 내부링크로
    - 예: `[extensibility](#5.-Extensibility)`

@ \`...\`

- 단어 자체가 강조된 부분이므로 번역하지 않고 `백틱`안에 원어 그대로 적기
- 간혹가다 "`object`를... object를..." 처럼 백틱된 단어가 한 문장/문단안에 있는 경우
  - "`object`를... 객체(object)를..." 처럼 해당 `백틱` 이후 첫 등장하는 단어에 번역(원문)으로 적기

@ 주석 양식

- `[//TODO]: # "TODO"`
- `[//Comment]: # "Comment"`
- `[//Link]: # "Link"`

@ Markdown triple-backtick (fence)에 사용한 언어 타입들

- json
- lang-none
