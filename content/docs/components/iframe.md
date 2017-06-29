---
$title@: Iframe
$category: Content
components:
  - iframe
$order: 115
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays an iframe.
href: /docs/components/iframe
---
<p>The IFrame component displays an iframe.</p>
<amp-iframe width="200" height="100"
    sandbox="allow-scripts allow-same-origin"
    layout="responsive"
    frameborder="0"
    src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDG9YXIhKBhqclZizcSzJ0ROiE0qgVfwzI&q=iceland">
</amp-iframe>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Src (https)</h3>
The URL of the page to embed.
<h3 class="mb3 mt3">Sandbox</h3>
Enables an extra set of restrictions for the content (for example: allow-same-origin, allow-scripts...)
<h3 class="mb3 mt3">Allow fullscreen</h3>
Indicates whether the frame is allowed to be placed into full screen mode.
<h3 class="mb3 mt3">Allow payment request</h3>
Indicates whether the Payment Request API may be invoked.
<h3 class="mb3 mt3">Allow transparency</h3>
Indicates whether the frame can be transparent.
<h3 class="mb3 mt3">Frame border</h3>
Specifies whether or not to display a border around the iframe (0 or 1).
<h3 class="mb3 mt3">Srcdoc</h3>
Specifies the HTML content of the page to show in the iframe.
<h3 class="mb3 mt3">Referrer policy</h3>
A string indicating which referrer to use when fetching the resource:

- "no-referrer" meaning that the Referer: header will not be sent.
- "no-referrer-when-downgrade" meaning that no Referer: header will be sent when navigating to an origin without TLS (HTTPS). This is a user agent’s default behavior, if no policy is otherwise specified.
- "origin" meaning that the referrer will be the origin of the page, that is roughly the scheme, the host and the port.
- "origin-when-cross-origin" meaning that navigations to other origins will be limited to the scheme, the host and the port, while navigations on the same origin will include the referrer's path.
- "unsafe-url" meaning that the referrer will include the origin and the path (but not the fragment, password, or username). This case is unsafe because it can leak origins and paths from TLS-protected resources to insecure origins.
