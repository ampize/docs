---
$title@: SEO
$order: 99
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/seo
---
<h2 class="mt4 mb4">Allow bot indexing</h2>
<p>By default, AMPize.me prevent new sites from being indexed indexed by search engines with a 'noindex,nofollow' meta tag.</p>
<p>To authorize bot indexing, just enable the 'Allow bot indexing' property in the Site Settings (SEO tab).</p>
<h2 class="mt4 mb4">Meta tags</h2>
<p>Meta tags provide information about the web page and are used by search engines to help categorize the page correctly.</p>
<p>AMPize.me allows you to specify the following SEO attributes:</p>

- Title
- Description
- Keywords

<p>These attributes can be specified in the Site Settings (SEO tab) and overridden for each page in the Page Settings (SEO tabs).</p>
<p>To add keywords, just press enter after each keyword.</p>
<h2 class="mt4 mb4">Structured data</h2>
<p>AMP pages that have structured data can appear in the Top stories carousel in search results. Without structured data, AMP pages can appear only as standard blue links in Google Search results.</p>
<p>AMPize.me will add a structured data element (JSON-LD markup) describing the current article in each page containing a 'Content Detail' component. This markup provides the following properties:</p>

- type: schema.org type. Must be configured in the data source. For a 'Site' source, select the correct 'Schema.org Type' in the first step ('Source'). Can be either NewsArticle, Article or BlogPosting.
- mainEntityOfPage: the canonical URL of the article page, determined automatically by AMPize.me 
- headline: the headline of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'headline' in the 'Schema.org output property' for the field that must be used as headline.
- image (URL, height and width): the representative image of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'image' in the 'Schema.org output property' for the field that must be used as an image. Beware! Images should be at least 696 pixels wide and in .jpg, .png, or. gif format. You can provide a default image in the Site Settings (SEO tab), that will be used if an article doesn't come with an image.
- publisher.name: The name of the publisher. Must be set in the Site Settings (SEO tab).
- publisher.logo: The logo of the publisher. Must be provided in the Site Settings (SEO tab). Beware! This logo must be in .jpg, .png, or .gif format, and should fit in a 60x600px rectangle, and either be exactly 60px high (preferred), or exactly 600px wide.
- datePublished: The date and time the article was first published. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'datePublished' in the 'Schema.org output property' for the field that must be used as a publication date.
- dateModified: The date and time the article was most recently modified. Can be declared in the data model of your data source (recommended, but not required). For a 'Site' source, in your Extraction template, select 'dateModified' in the 'Schema.org output property' for the field that must be used as a modification date.
- author.name: The name of the author of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'author.name' in the 'Schema.org output property' for the field that must be used as the author name. You can set a default author name in the Site Settings (SEO tab), that will be used if an article doesn't come with an author name.
- description: A short description of the article. Can be declared in the data model of your data source (recommended, but not required). For a 'Site' source, in your Extraction template, select 'description' in the 'Schema.org output property' for the field that must be used as a description.

<h2 class="mt4 mb4">How to make your AMP pages discoverable?</h2>
<p>So that Google easily find your AMP pages, you should add to your non-AMP pages links to the AMP versions, using the following tag in the `<head>` section of your page:</p>
```
<link rel="amphtml" href="https://www.example.com/url/to/amp/document.html">
```
<p>To get the URL of detail pages, you can use the API of AMPize.me.</p> 
<p>The head of AMP pages should also contain a link tag, to the related non-AMP version of the page. To do so, you should fill in the 'Canonical URL' field in the Page Settings (SEO tab). Detail pages will automatically include such a tag, provided that you enable the 'Use original URL as canonical' option in the Site Settings (SEO tab).</p>
