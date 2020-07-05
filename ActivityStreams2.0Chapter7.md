[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 7. [보안 고려사항 (Security Considerations)](ActivityStreams2.0Contents.md#목차-table-of-contents)

Publishers or Consumers implementing Activity Streams as a stream of public data may also want to consider the potential for unsolicited commercial or malicious content and should take preventative measures to recognize such content and either identify it or not include it in their implementations.

Activity Streams 을 공개 데이터 스트림으로 구현하는 게시자 또는 소비자는 요청하지 않은 상업용 또는 악성 컨텐츠의 가능성을 고려할수 있으며, 이를 식별하거나 구현에 포함하지 않는 예방 조치를 취해야합니다.

Publishers should take reasonable measures to ensure potentially malicious user input such as cross-site scripting attacks are not included in the Activity Streams data they publish.

게시자는 게시하는 Activity Streams 데이터에 크로스-사이트 스크립팅 공격같은 잠재적으로 악의적인 사용자 입력이 포함되지 않도록 적절한 조치를 취해야 합니다.

Consumers that re-emit ingested content to end-users *MUST* take reasonable measures if emitting ingested content to make sure potentially malicious ingested input is not re-emitted.

수집된 컨텐츠를 최종 사용자에게 다시 전송하는 소비자는 수집된 컨텐츠를 방출할 경우 *반드시* 악의적으로 수집된 입력이 다시 전송되지 않도록 합리적인 조치를 취해야 합니다.

Consumers that re-emit ingested content for crawling by search engines should take reasonable measures to limit any use of their site as a Search Engine Optimization loophole. This may include converting untrusted hyperlinks to text or including a rel="nofollow" attribute.

검색 엔진에서 크롤링하기 위해 수집된 컨텐츠를 다시 전송하는 소비자는 자신의 사이트를 검색 엔진 최적화 허점을 통해 사용하는것을 하지 못하도록 합리적인 조치를 취해야 합니다. 여기에는 신뢰할수 없는 하이퍼링크를 텍스트로 변환하거나 rel="nofollow" 속성을 사용하는 방법 등이 포함됩니다.

Consumers should be aware of the potential for spoofing attacks where the attacker publishes activities or objects with falsified property values with the intent of injecting malicious content, hiding or corrupting legitimate content, or misleading users.

소비자는 공격자가 악의적인 컨텐츠를 주입하거나 합법적인 컨텐츠를 숨기거나, 손상시키거나, 사용자를 속이려는 목적으로 위조된 속성 값을 가진 액티비티 또는 객체를 게시하는 스푸핑 공격의 가능성을 알아야 합니다.

Activity Streams are JSON Documents and are subject to the same security considerations described in [[RFC7159](ActivityStreams2.0ChapterF.md#rfc7159)].

Activity Streams는 JSON 문서이며 [[RFC7159](ActivityStreams2.0ChapterF.md#rfc7159)] 에 설명된 것과 동일한 보안 고려사항이 적용됩니다.

Activity Streams implementations handle URIs. See Section 7 of [ [RFC3986](ActivityStreams2.0ChapterF.md#rfc3986)].

Activity Streams 구현은 URI를 처리합니다. [ [RFC3986](ActivityStreams2.0ChapterF.md#rfc3986)] 의 섹션 7을 참조하시길 바랍니다.

Activity Streams implementations handle IRIs. See Section 8 of [ [RFC3987](ActivityStreams2.0ChapterF.md#rfc3987)].

Activity Streams 구현은 IRI를 처리합니다. [ [RFC3987](ActivityStreams2.0ChapterF.md#rfc3987)] 의 섹션8을 참조하시길 바랍니다.

[맨 위로](#7-보안-고려사항-security-considerations)
