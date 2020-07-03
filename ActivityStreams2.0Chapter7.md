[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 7. Security Considerations

Publishers or Consumers implementing Activity Streams as a stream of public data may also want to consider the potential for unsolicited commercial or malicious content and should take preventative measures to recognize such content and either identify it or not include it in their implementations.

Publishers should take reasonable measures to ensure potentially malicious user input such as cross-site scripting attacks are not included in the Activity Streams data they publish.

Consumers that re-emit ingested content to end-users *MUST* take reasonable measures if emitting ingested content to make sure potentially malicious ingested input is not re-emitted.

Consumers that re-emit ingested content for crawling by search engines should take reasonable measures to limit any use of their site as a Search Engine Optimization loophole. This may include converting untrusted hyperlinks to text or including a rel="nofollow" attribute.

Consumers should be aware of the potential for spoofing attacks where the attacker publishes activities or objects with falsified property values with the intent of injecting malicious content, hiding or corrupting legitimate content, or misleading users.

Activity Streams are JSON Documents and are subject to the same security considerations described in [[RFC7159](https://www.w3.org/TR/activitystreams-core/#bib-RFC7159)].

Activity Streams implementations handle URIs. See Section 7 of [ [RFC3986](https://www.w3.org/TR/activitystreams-core/#bib-RFC3986)].

Activity Streams implementations handle IRIs. See Section 8 of [ [RFC3987](https://www.w3.org/TR/activitystreams-core/#bib-RFC3987)].
