---
$title@: AMP Validation
$order: 11
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
description: >

href: /docs/guides/ampvalidation
---

By default, AMPize.me prevents publishing of invalid AMP pages by running an internal validation process prior to every site publication action.

In case of success, the publication process is silently continued.  
An alert is displayed if validation errors are discovered.

<amp-img src="/static/img/validation-alert.png"  width="385"  height="194"  layout="fixed" alt="settings"></amp-img>

## Dealing with errors

The error report gives several pieces of information about each error:

* Its location (line and column) in the code
* A textual description of the error
* A link to a relevant document

<amp-img src="/static/img/validation-report.png"  width="1628"  height="835"  layout="responsive" alt="settings"></amp-img>

Additional information about AMP pages debugging can be found on **[the AMP project website](https://www.ampproject.org/docs/guides/validate)**.

Keep in mind that the validation process occurs only at publishing time: in some rare cases, some dynamic content (for example invalid third party HTML conversion to AMP HTML) can cause subsequent AMP validation problems.
