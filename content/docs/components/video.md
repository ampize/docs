---
$title@: Video
$category: Media
components:
  - video
$order: 385
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays an embedded HTML5 video file
href: /docs/components/video
---
<p>The Audio component displays an embedded HTML5 video file.</p>
<amp-video width="480"
  height="270"
  src="https://ampbyexample.com/video/tokyo.mp4"
  poster="https://ampbyexample.com/img/tokyo.jpg"
  layout="responsive"
  controls>
  <source type="video/mp4"
    src="https://ampbyexample.com/video/tokyo.mp4">
  <source type="video/webm"
    src="https://ampbyexample.com/video/tokyo.webm">
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
