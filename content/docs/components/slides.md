---
$title@: Slides
$category: Content
$order: 130
components:
  - carousel
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays multiple similar pieces of content along a horizontal axis, showing a single slide at a time.
href: /docs/components/slides
---
<p>The Slides components displays multiple similar pieces of content along a horizontal axis, showing a single slide at a time</p>
<amp-carousel width="400"
  height="300"
  layout="responsive"
  type="slides">
  <amp-img src="https://ampbyexample.com/img/image1.jpg"
    width="400"
    height="300"
    layout="responsive"
    alt="a sample image"></amp-img>
  <amp-img src="https://ampbyexample.com/img/image2.jpg"
    width="400"
    height="300"
    layout="responsive"
    alt="another sample image"></amp-img>
  <amp-img src="https://ampbyexample.com/img/image3.jpg"
    width="400"
    height="300"
    layout="responsive"
    alt="and another sample image"></amp-img>
</amp-carousel>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Detail page</h3>
Page of the site (containing a Detail component) to which the user should be redirected when clicking on a slide.
<h3 class="mb3 mt3">Display controls arrows on mobile</h3>
Indicates whether left and right arrows are displayed for the user to navigate carousel items on mobile devices.
<h3 class="mb3 mt3">Number of slides</h3>
Number of slides displayed in the carousel
<h3 class="mb3 mt3">Offset</h3>
The number of items to skip in the query results.
<h3 class="mb3 mt3">Loop</h3>
Allows the user to advance past the first item or the final item. There must be at least 3 slides for looping to occur. 
<h3 class="mb3 mt3">Autoplay</h3>
If checked, advances the slide to the next slide without user interaction.

