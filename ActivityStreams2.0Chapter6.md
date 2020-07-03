[목차로 돌아가기](ActivityStreams2.0Contents.md)

## 6. Privacy Considerations

Activity Streams 2.0 documents can (and likely will) contain potentially sensitive personal information such as identity, contact information, physical location, physical characteristics, and so forth. Furthermore, Activity data, in general, can be analyzed to generate profiles of the behavior of individual or groups of Actors.

Implementations that produce or consume Activity Streams 2.0 documents *MUST* take steps to openly and publicly document and communicate to all potential users: (a) the kinds of potentially sensitive personal information published, consumed or collected by the implementation, (b) the reasons for publishing, consuming and collecting that information, (c) the manner in which that information is being used, (d) the identity of any other party with whom that information is being shared, and (e) the reason the information is being shared with other parties.

Implementations that publish Activity Streams 2.0 documents *SHOULD* assume a default position of limiting both the kind and amount of sensitive personal information included in the document unless users have "opted in" to sharing additional detail.

Implementations that consume Activity Streams 2.0 documents *SHOULD NOT*, by default, store or share sensitive personal information included within consumed documents unless users have "opted in" to allowing that information to be stored or shared.

In this context, "opting in" does not necessarily require explicit action on the part of the user. If, for instance, the use of certain sensitive personal information is clearly implicit in the use of an implementation (a location tracking service, for example), then any use of that implementation can be considered an implicit acknowledgement that the sensitive personal information will be used and shared so long as the documentation guidelines listed above are followed.