---
$title@: Plugging a website
$order: 2
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/crawl
---
<p>If you can't connect AMPize to your database and you don't have any REST API, you still can scrape and normalize content from an existing website. In this guide, you'll learn how to crawl websites with AMPize.</p>
<h2 class="mt4 mb4">Overview</h2>
<p>By plugging a website as a datasource, you can extract structured items from a site. Your site will be spidered from a starting seed URL, and all pages matching the extraction template you defined will be processed.</p>
<p>You can optionally set crawl jobs to repeat automatically.</p>
<p>During crawls, only new items are extracted. Items are updated when displayed by a visitor in the AMP site, and will be deleted if the source page doesn't exist anymore.</p>
<h2 class="mt4 mb4">Settings</h2>
<h3 class="mb3 mt3">Name</h3>
<p>Name of your datasource. Cannot contain spaces, special caracters or numbers. The datasource name cannot be modified afterwards.</p>
<h3 class="mb3 mt3">Source URL</h3>
<p>Starting or seed URL from which your site will be spidered.</p>
<h3 class="mb3 mt3">Template URL</h3>
<p>URL of a classic detail page of your site, in which a complete article is displayed.</p>
<h3 class="mb3 mt3">Schema.org Type</h3>
<p>Type of content for this source, used to describe your items through JSON-LD markup (see <a href="docs/guides/seo">SEO</a> guide).</p>
<h3 class="mb3 mt3">User agent</h3>
<p>User agent used by the web spiders. Can be useful to let spiders access content that are usually blocked by a paywall for example.</p>
<h3 class="mb3 mt3">Crawl RegEx</h3>
<p>Only URLs containing at least one of the matching strings will be crawled. A page is said to be crawled when it is evaluated for additional links to follow, or for links to be processed.</p>
<h3 class="mb3 mt3">Processing RegEx</h3>
<p>Only URLs containing at least one of the matching strings will be processed. A web page is said to be processed if it matches the extraction template.</p>
<h3 class="mb3 mt3">Excluding RegEx</h3>
<p>URLs containing at least one of the matching strings will not be crawled.</p>
<h3 class="mb3 mt3">Obey robots.txt</h3>
<p>If enabled, crawls will respect robots.txt policies. When turned off, robots.txt will be ignored</p>
<h3 class="mb3 mt3">Max pages to process</h3>
<p>Limit the number of processed pages</p>
<h3 class="mb3 mt3">Max items</h3>
<p>Limit the number of extracted items</p>
<h3 class="mb3 mt3">Max depth</h3>
<p>The maximum depth (number of clicks you need to reach a specific page from the starting URL) that will be allowed to crawl for your site.</p>
<h3 class="mb3 mt3">Target Crawl Concurrency</h3>
<p>Average number of requests send in parallel to your website.</p>
<h3 class="mb3 mt3">Repeat crawl</h3>
<p>If enabled, crawl jobs will repeat automatically. Each round will fully re-spider the site from the starting URL, and process pages according to your settings.</p>
<h3 class="mb3 mt3">Repeat frequency (in minutes)</h3>
<p>The crawl will repeat every x minutes.</p>
<h3 class="mb3 mt3">Email notification</h3>
<p>You can choose to be notified by email at the conclusion of each crawl.</p>
<h2 class="mt4 mb4">Extraction template</h2>
<p>The extraction template will help you define the structure of your data. You can add fields to the structure from:</p>

- CSS selectors matching specific elements in the page
- markup vocabularies (JSON-LD or microdata)

<h3 class="mb3 mt3">CSS selectors</h3>
<p>To add a field to your structure, just click on an element of the page and select the attribute (text, html, src, href, alt...) you want to be used for this field. You can use several attributes for the same element if you want (for example, for an image you can add an 'image' field for the 'src' attribute and a 'caption' field for the 'alt' attribute).</p>
<p>You can also manually edit the CSS selector if you cannot reach an element using the interface.</p>
<p>For each field, the following propertiers are available:</p>

- Field name (mandatory)
- Format (for 'text' attributes only): 'text' or 'date'. If 'date', the value will be converted to a timestamp
- Required: if checked, items without this field won't be scraped
- Schema.org output property: select the corresponding property for the generated JSON-LD markup (see <a href="docs/guides/seo">SEO</a> guide)

<p>Once added, a field can not be modified: you must delete it and add it all over again.</p>
<h3 class="mb3 mt3">Markup vocabularies</h3>
<p>If the page you choose as a template contains JSON-LD or microdata markup, a button labelled 'Add a field from markup' will let you add a field based on one of these properties often used for Article items:</p>

- description
- headline
- articleBody
- datePublished
- dateModified
- dateCreated
- thumbnailUrl
- image.url
- author.name
- creator.name

<p>As for fields based on CSS selectors, you must give it a name and you can select a schema.org output property if you want this field to be used for the generated JSON-LD markup (see <a href="docs/guides/seo">SEO</a> guide).</p>
<h2 class="mt4 mb4">Manage list queries</h2>
<p>If you want to display article lists on your AMP site that perfectly match the corresponding list on your source site, you can manage list queries.</p>
<p>Such a list query is defined by:</p>

- the name of your choice
- the page URL from the source site
- the CSS selector that matches the div tag surrounding the list of articles on this page

<p>Once you have defined a list query, you can use it for any of your AMP sites in the <a href="docs/guides/querybuilder">Query Builder</a>. To mimic the list of your source site, you just have to apply a filter (yourQueryListName_tag = TRUE) and a sort property (order by: yourQueryListName_order, direction: Ascendant) on your query.</p>
<h2 class="mt4 mb4">Other actions</h2>
<p>For each site source, the following actions are available:</p>
<h3 class="mb3 mt3">Run/Stop</h3>
<p>To run/stop the crawl manually.</p>
<h3 class="mb3 mt3">Crawl specific URLs</h3>
<p>If you want an item to be extracted without having to wait for the next round, you can crawl specific URLs.</p>
<h3 class="mb3 mt3">Delete data</h3>
<p>To delete all the items already extracted. The settings of your source and the extraction template are unaffected.</p>
<h3 class="mb3 mt3">Delete source</h3>
<p>To delete the whole source (items, settings, extraction template).</p>
