---
$title@: Video
$category: Media
components:
  - video
$order: 0
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays an embedded HTML5 video file
href: /docs/components/video
---
<p>The Audio component displays an embedded HTML5 video file.</p>
<amp-video controls
  width="640"
  height="360"
  layout="responsive"
  poster="images/kitten-playing.png">
  <source src="videos/kitten-playing.webm"
    type="video/webm" />
  <source src="videos/kitten-playing.mp4"
    type="video/mp4" />
  <div fallback>
    <p>This browser does not support the video element.</p>
  </div>
</amp-video>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Source URL</h3>
The video resource URL. It must be HTTPS.
<h3 class="mb3 mt3">Poster URL</h3>
The image for the frame to be displayed before video playback has started. By default, the first frame is displayed.
<h3 class="mb3 mt3">Display controls</h3>
If checked, the browser offers controls to allow the user to control video playback.
<h3 class="mb3 mt3">Loop</h3>
If checked, the video will automatically loop back to the start upon reaching the end.
<h3 class="mb3 mt3">Autoplay</h3>
If checked, the video will start playing as soon as it is ready.
