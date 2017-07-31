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
