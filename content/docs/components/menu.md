---
$title@: Menu
$category: Navigation
$order: 0
isDraft: 0
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >
    Displays a navigation menu.
href: /docs/components/menu
---
<p>The Menu component displays a responsive navigation toolbar, built from the pages tree.</p>
<amp-img width=496 height=396 src="/static/img/components/menu.png" layout="fixed"></amp-img>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Root</h3>
The start page to generate the menu, usually the Home page.
<h3 class="mb3 mt3">Logo Url</h3>
Optional logo url.  
You can use the media picker to upload your logo or select an image from a data source.
<h3 class="mb3 mt3">Display root</h3>
Set to True to display the root page in the menu.
<h3 class="mb3 mt3">Fallback root</h3>
The fallback root is used when the root page is not set.

- Current: the current page is used as root page.
- Parent: the parent page in the pages tree is used as root page.

Default to Current.

<h3 class="mb3 mt3">Base level</h3>
The number of levels to display from the root page.

Default to 1.
