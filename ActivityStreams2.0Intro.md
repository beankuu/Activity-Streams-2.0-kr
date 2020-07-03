[목차로 돌아가기](ActivityStreams2.0Contents.md)

# [액티비티스트림(Activity Streams) 2.0](https://www.w3.org/TR/activitystreams-core/)
<abbr title="World Wide Web Consortium">W3C</abbr> Recommendation 23 May 2017

**This version:**
- https://www.w3.org/TR/2017/REC-activitystreams-core-20170523/

**Latest published version:**
- https://www.w3.org/TR/activitystreams-core/

**Latest editor's draft:**
- http://w3c.github.io/activitystreams/core/

**Test suite:**
- https://github.com/w3c/activitystreams/tree/master/test

**Implementation report:**
- https://github.com/w3c/activitystreams/tree/master/implementation-reports

**Previous version:**
- https://www.w3.org/TR/2017/PR-activitystreams-core-20170413/

**Editors:**
- [James M Snell](http://jasnell.me/), IBM 
- [Evan Prodromou](https://fuzzy.ai/about), Fuzzy.ai 

**Repository:**
- [Github](https://github.com/w3c/activitystreams) 
- [Issues](https://github.com/w3c/activitystreams/issues) 
- [Commits](https://github.com/w3c/activitystreams/commits/master) 

**Test:**
- [Validator](https://as2.rocks/) 

Please check the [**errata**](https://github.com/w3c/activitystreams/blob/master/ERRATA.md) for any errors or issues reported since publication.

The English version of this specification is the only normative version. Non-normative [translations](https://www.w3.org/2003/03/Translations/byTechnology?technology=https://www.w3.org/TR/activitystreams-vocabulary/) may also be available.

[Copyright](https://www.w3.org/Consortium/Legal/ipr-notice#Copyright) © 2017 [<abbr title="World Wide Web Consortium">W3C</abbr>](https://www.w3.org/)® (<abbr title="Massachusetts Institute of Technology">[MIT](https://www.csail.mit.edu/)</abbr>, <abbr title="European Research Consortium for Informatics and Mathematics">[ERCIM](https://www.ercim.eu/)</abbr>, [Keio](https://www.keio.ac.jp/), [Beihang](http://ev.buaa.edu.cn/)). <abbr title="World Wide Web Consortium">W3C</abbr> [liability](https://www.w3.org/Consortium/Legal/ipr-notice#Legal_Disclaimer), [trademark](https://www.w3.org/Consortium/Legal/ipr-notice#W3C_Trademarks) and [permissive document license](https://www.w3.org/Consortium/Legal/2015/copyright-software-and-document) rules apply.

-----

## Abstract

This specification details a model for representing potential and completed activities using the JSON format. It is intended to be used with vocabularies that detail the structure of activities, and define specific types of activities.

### Author's Note

_This section is non-normative._

This draft is heavily influenced by the JSON Activity Streams 1.0 specification originally co-authored by Martin Atkins, Will Norris, Chris Messina, Monica Wilkinson, Rob Dolin and James Snell. The author is very thankful for their significant contributions and gladly stands on their shoulders. Some portions of the original text of Activity Streams 1.0 are used in this document.

## Status of This Document

This section describes the status of this document at the time of its publication. Other documents may supersede this document. A list of current <abbr title="World Wide Web Consortium">W3C</abbr> publications and the latest revision of this technical report can be found in the [<abbr title="World Wide Web Consortium">W3C</abbr> technical reports index](https://www.w3.org/TR/) at https://www.w3.org/TR/.

This document was published by the [Social Web Working Group](https://www.w3.org/Social/WG) as a Recommendation. Comments regarding this document are welcome. Please send them to [public-socialweb@w3.org](public-socialweb@w3.org) ([subscribe](public-socialweb-request@w3.org), [archives](https://lists.w3.org/Archives/Public/public-socialweb/)).

Please see the Working Group's [implementation report](https://github.com/w3c/activitystreams/tree/master/implementation-reports).

This document has been reviewed by <abbr title="World Wide Web Consortium">W3C</abbr> Members, by software developers, and by other <abbr title="World Wide Web Consortium">W3C</abbr> groups and interested parties, and is endorsed by the Director as a <abbr title="World Wide Web Consortium">W3C</abbr> Recommendation. It is a stable document and may be used as reference material or cited from another document. <abbr title="World Wide Web Consortium">W3C</abbr>'s role in making the Recommendation is to draw attention to the specification and to promote its widespread deployment. This enhances the functionality and interoperability of the Web.

This document was produced by a group operating under the [5 February 2004 <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy-20040205/). <abbr title="World Wide Web Consortium">W3C</abbr> maintains a [public list of any patent disclosures](https://www.w3.org/2004/01/pp-impl/72531/status) made in connection with the deliverables of the group; that page also includes instructions for disclosing a patent. An individual who has actual knowledge of a patent which the individual believes contains [Essential Claim(s)](https://www.w3.org/Consortium/Patent-Policy-20040205/#def-essential) must disclose the information in accordance with [section 6 of the <abbr title="World Wide Web Consortium">W3C</abbr> Patent Policy](https://www.w3.org/Consortium/Patent-Policy-20040205/#sec-Disclosure).

This document is governed by the [1 March 2017 <abbr title="World Wide Web Consortium">W3C</abbr> Process Document](https://www.w3.org/2017/Process-20170301/).
