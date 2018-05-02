---
$title@: Reddit
$category: Social
$order: 420
components:
  - reddit
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays a Reddit comment or post embed.
href: /docs/components/reddit
---
<p>The Reddit component displays a Reddit comment or post embed.</p>
<amp-reddit
  layout="responsive"
  width="300"
  height="400"
  data-embedtype="post"
  data-src="https://www.reddit.com/r/me_irl/comments/52rmir/me_irl/?ref=share&amp;ref_source=embed">
</amp-reddit>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Embed type</h3>

- Post
- Comment

<h3 class="mb3 mt3">Permalink uri</h3>
The permalink uri for the post or comment.
<h3 class="mb3 mt3">Embed Comment UUID</h3>
The provided UUID for the comment embed.
<h3 class="mb3 mt3">Embed Comment datetime string</h3>
The datetime string for the comment embed.
<h3 class="mb3 mt3">Embed Parent Comment</h3>
Indicates whether the parent comment should be included in the embed.
<h3 class="mb3 mt3">Live update</h3>
Indicates whether the embedded comment should update if the original comment is updated.
