---
$title@: YouTube
$category: Media
$order: 1
components:
  - youtube
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays a YouTube video.
href: /docs/components/youtube
---
<p>The YouTube component displays a YouTube video.</p>
<amp-youtube width="480"
  height="270"
  layout="responsive"
  data-videoid="lBTCB7yLs8Y">
</amp-youtube>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Video ID</h3>
The YouTube video id found in every video page URL.
<h3 class="mb3 mt3">Autoplay</h3>
If checked, the video will start playing as soon as it is ready.
<h3 class="mb3 mt3">Controls</h3>
Indicates whether the video player controls are displayed.

- 0 – Player controls do not display in the player. For IFrame embeds, the Flash player loads immediately.
- 1 (default) – Player controls display in the player. For IFrame embeds, the controls display immediately and the Flash player also loads immediately.
- 2 – Player controls display in the player. For IFrame embeds, the controls display and the Flash player loads after the user initiates the video playback.

<h3 class="mb3 mt3">Playlist</h3>
Comma-separated list of video IDs to play.
