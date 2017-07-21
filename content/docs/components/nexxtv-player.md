---
$title@: NexxTV Player
$category: Media
components:
  - nexxtv-player
$order: 353
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays a media stream from the nexxOMNIA platform.
href: /docs/components/nexxtv-player
---
<p>The NexxTV component displays a media stream from the nexxOMNIA platform.</p>
<amp-nexxtv-player
    data-mediaid="PTPFEC4U184674"
    data-client="583"
    data-streamtype="video"
    data-seek-to="2"
    data-mode="static"
    data-origin="https://embed.nexx.cloud/"
    data-disable-ads="1"
    layout="responsive"
    width="480" height="270"></amp-nexxtv-player>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Domain ID</h3>
Your domain ID.
<h3 class="mb3 mt3">Media ID</h3>
Represents the ID of the media you want to play.
<h3 class="mb3 mt3">Streaming type</h3>
Indicates the media streaming type, which can be one of the following:

- video (default)
- audio
- playlist
- playlist-masked: A playlist without the option to skip or choose video.
- live
- album: An audio playlist.

<h3 class="mb3 mt3">Starting point</h3>
Indicates the starting point of your media (in seconds). For example, video starting 1:30min.
<h3 class="mb3 mt3">Mode</h3>
Indicates the data mode : 

- static (default)
- api

<h3 class="mb3 mt3">Source domain</h3>
Indicates the source from which the embedded domain media is played. By default this is set to https://embed.nexx.cloud/.
<h3 class="mb3 mt3">Disable Ads</h3>
If checked, disables Ads.
