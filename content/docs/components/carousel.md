---
$title@: Carousel
$category: Content
components:
  - carousel
$order: 100
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays multiple similar pieces of content along a horizontal axis, all slides being shown.
href: /docs/components/carousel
---
<p>The Carousel components displays multiple similar pieces of content along a horizontal axis, all slides being shown.</p>
<amp-carousel height="300"
  layout="fixed-height"
  type="carousel">
  <amp-img src="https://ampbyexample.com/img/image1.jpg"
    width="400"
    height="300"
    alt="a sample image"></amp-img>
  <amp-img src="https://ampbyexample.com/img/image2.jpg"
    width="400"
    height="300"
    alt="another sample image"></amp-img>
  <amp-img src="https://ampbyexample.com/img/image3.jpg"
    width="400"
    height="300"
    alt="and another sample image"></amp-img>
</amp-carousel>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Detail page</h3>
Page of the site (containing a Detail component) to which the user should be redirected when clicking on a slide.
<h3 class="mb3 mt3">Number of slides</h3>
Number of slides displayed in the carousel
<h3 class="mb3 mt3">Offset</h3>
The number of items to skip in the query results.
<h3 class="mb3 mt3">Display controls arrows on mobile</h3>
Indicates whether left and right arrows are displayed for the user to navigate carousel items on mobile devices.
