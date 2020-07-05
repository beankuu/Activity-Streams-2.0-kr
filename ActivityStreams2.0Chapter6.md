[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 6. [개인정보 고려사항 (Privacy Considerations)](ActivityStreams2.0Contents.md#목차-table-of-contents)

Activity Streams 2.0 documents can (and likely will) contain potentially sensitive personal information such as identity, contact information, physical location, physical characteristics, and so forth. Furthermore, Activity data, in general, can be analyzed to generate profiles of the behavior of individual or groups of Actors.

Activity Streams 2.0 문서에는 ID, 연락처 정보, 물리적 위치, 물리적 특성 등과 같은 잠재적으로 중요한 개인 정보를 포함할 가능성이 (많이) 있습니다. 또한 일반적으로 Activity 데이터를 분석하여 개별 또는 액터 그룹의 행동에 대한 프로필을 생성할 수 있습니다.

Implementations that produce or consume Activity Streams 2.0 documents *MUST* take steps to openly and publicly document and communicate to all potential users: (a) the kinds of potentially sensitive personal information published, consumed or collected by the implementation, (b) the reasons for publishing, consuming and collecting that information, (c) the manner in which that information is being used, (d) the identity of any other party with whom that information is being shared, and (e) the reason the information is being shared with other parties.

Activity Streams 2.0 문서를 생성하거나 소비하는 구현은 *반드시* 모든 잠재적 사용자에게 공개적으로 문서화하고 정보를 전달하는 단계를 수행해야 합니다: (a) 구현에 의해 게시, 소비 또는 수집된 잠재적으로 민감한 개인정보의 종류, (b) 해당 정보를 게시, 소비 및 수집하는 이유, (c) 해당 정보가 사용되는 방식, (d) 정보가 공유되는 다른 당사자의 신원, 그리고 (d) 정보가 제3자와 공유되는 이유.

Implementations that publish Activity Streams 2.0 documents *SHOULD* assume a default position of limiting both the kind and amount of sensitive personal information included in the document unless users have "opted in" to sharing additional detail.

Activity Streams 2.0 문서를 게시하는 구현에서는 사용자가 추가 세부 정보를 "옵트인(opted in)" 하지 않는 한, 문서에 포함된 중요한 개인 정보의 종류와 양을 모두 제한하는 기본 입장을 *취해야 합니다*.

Implementations that consume Activity Streams 2.0 documents *SHOULD NOT*, by default, store or share sensitive personal information included within consumed documents unless users have "opted in" to allowing that information to be stored or shared.

Activity Streams 2.0 문서를 사용하는 구현에서는 사용자가 해당 정보를 저장하거나 공유하도록 "옵트인" 을 하지 않는한 기본적으로 사용된 문서에 포함된 중요한 개인 정보를 저장하거나 공유해서는 *안 됩니다*.

In this context, "opting in" does not necessarily require explicit action on the part of the user. If, for instance, the use of certain sensitive personal information is clearly implicit in the use of an implementation (a location tracking service, for example), then any use of that implementation can be considered an implicit acknowledgement that the sensitive personal information will be used and shared so long as the documentation guidelines listed above are followed.

이러한 맥락에서, "옵트인"은 사용자 측에서 명시적인 작업을 요구하지 않습니다. 예를 들어, 특정 민감한 개인 정보의 사용이 구현(예: 위치 추적 서비스)의 사용에 분명히 포함되어 있는 경우, 해당 구현의 모든 사용은 문서 지침이 있는 한 중요한 개인 정보가 사용 및 공유될 것임을 암시적으로 인정하는 것으로 간주될 수 있습니다.

[맨 위로](#6-개인정보-고려사항-privacy-considerations)
