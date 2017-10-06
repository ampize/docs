---
$title@: Plugging a paywall
$order: 13
isDraft: 0
$date: 2017-03-17
$dates:
  published: 2017-03-17
description: >

href: /docs/guides/paywall
---
## Implementing a paywall

The best way to implement a paywall in AMPize is to use amp-access.
Since the [official tutorial](https://ampbyexample.com/components/amp-access/) is quite thorough we won't be explaining the details of amp-access in this guide so be sure to read it before proceeding.

In the next part we will simply cover the implementation of the same tutorial on an AMPize website.

AMPize has a tab in the site settings interface dedicated to amp-access. Simply fill-in the json field with the amp-access configuration json such as the one in the tutorial :

```javascript
 {
      "authorization": "https://ampbyexample.com/components/amp-access/authorization?rid=READER_ID&url=CANONICAL_URL&ref=DOCUMENT_REFERRER&_=RANDOM",
      "pingback": "https://ampbyexample.com/components/amp-access/authorization?rid=READER_ID&url=CANONICAL_URL&ref=DOCUMENT_REFERRER&_=RANDOM",
      "login": {
        "sign-in": "https://ampbyexample.com/components/amp-access/login?rid=READER_ID&url=CANONICAL_URL",
        "sign-out": "https://ampbyexample.com/components/amp-access/logout"
      },
      "authorizationFallbackResponse": {
          "error": true,
          "access": false,
          "subscriber": false
      }
  }
```

You can then add code such as `amp-access="access"` in a Mustache template or even a template override on any component in your website. We recommend that you experiment with the different code samples presented in the tutorial.
