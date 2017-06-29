---
$title@: Animation
$category: Media
$order: 300
components:
  - anim
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays a runtime-managed animated image, typically a GIF.
href: /docs/components/animation
---
<p>The Animation component displays a runtime-managed animated image (typically a GIF).</p>
<amp-anim width="245"
  height="300"
  src="https://ampbyexample.com/img/gopher.gif"
  alt="an animation"
  attribution="The Go gopher was designed by Reneee French and is licensed under CC 3.0 attributions.">
</amp-anim>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Image URL</h3>
The URL that points to the animated image file.
<h3 class="mb3 mt3">Alternate Text (alt)</h3>
A string of alternate text.
<h3 class="mb3 mt3">Attribution</h3>
The attribution of the image (for example: 'The Go gopher was designed by Reneee French and is licensed under CC 3.0 attributions')
<h3 class="mb3 mt3">srcset Attribute</h3>
The URL of the image to use in different situations. It allows you to define multiple sizes of the same image, allowing the browser to select the appropriate image source.
