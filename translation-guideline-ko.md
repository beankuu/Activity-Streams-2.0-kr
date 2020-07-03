[README로 돌아가기](README.md)

# ActivityStreams2.0 문서 한글 번역 가이드라인

- 임시로 작성한 문서입니다.
- ActivityPub / ActivityStreams2.0 번역 가이드라인들과 내용이 유사합니다.

## 1. 번역 단어관련

- 타 문서에서는 음차로 번역되나, 이 문서에서는 한글로 번역한 단어가 다수 존재합니다.

원문 | 번역 | 비고
-- | -- | --

### 1-1. 음차를 사용하는 번역

원문 | 번역 | 비고
-- | -- | --

### 1-2. 원문 그대로 사용하는 번역

원문 | 비고
-- | --

## 2. 번역 일관성

RFC2119 (Chapter1에 정의되어 있습니다)

- ~수도 있다 (MAY),
- 반드시 (MUST),
- 절대 하지 말아야 (MUST NOT),
- 권장된다 (SHOULD),
- 권장되지 않는다 (SHOULD NOT)

## 3. markdown 등 그 외 관련

`[WORD](LINK)`

- WORD
  - {번역한 단어}를 사용하되, 의미전달이 애매할 경우는 {번역(원문)}

- LINK
  - 개별 파일에서는 원문 링크를 따르기
    - 예: `[Extensibility](https://www.w3.org/TR/activitystreams-core/#extensibility)`
  - [종합본](ActivityVocabulary.md)에는 최대한 내부링크로
    - 예: `[extensibility](#5.-Extensibility)`

\`...\`

- 단어 자체가 강조된 부분이므로 번역하지 않고 `백틱`안에 원어 그대로 적기
- 간혹가다 "`object`를... object를..." 처럼 백틱된 단어가 한 문장/문단안에 있는 경우
  - "`object`를... 객체(object)를..." 처럼 해당 `백틱` 이후 첫 등장하는 단어에 번역(원문)으로 적기

주석 양식

- `[//TODO]: # "TODO"`
- `[//Comment]: # "Comment"`
- `[//Link]: # "Link"`
