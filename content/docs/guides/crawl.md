---
$title@: Plugging a Website
$order: 2
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
description: >

href: /docs/guides/crawl
---
If you can't connect AMPize to your database and you don't have any REST API, you still can scrape and normalize content from an existing website. In this guide, you'll learn how to crawl websites with AMPize.

## Overview

By plugging a website as a datasource, you can extract structured items from a site. Your site will be spidered from a starting seed URL, and all pages matching the extraction template you defined will be processed.

You can optionally set crawl jobs to repeat automatically.

During crawls, only new items are extracted. Items are updated when displayed by a visitor in the AMP site, and will be deleted if the source page doesn't exist anymore.

## Settings

### Name

Name of your datasource. Cannot contain spaces, special caracters or numbers. The datasource name cannot be modified afterwards.

### Source URL

Starting or seed URL from which your site will be spidered.

### Template URL

URL of a classic detail page of your site, in which a complete article is displayed.

### Schema.org Type

Type of content for this source, used to describe your items through JSON-LD markup (see [SEO](/docs/guides/seo) guide).

### User agent

User agent used by the web spiders. Can be useful to let spiders access content that are usually blocked by a paywall for example.

### Crawl RegEx

Only URLs containing at least one of the matching strings will be crawled. A page is said to be crawled when it is evaluated for additional links to follow, or for links to be processed.

### Processing RegEx

Only URLs containing at least one of the matching strings will be processed. A web page is said to be processed if it matches the extraction template.

### Excluding RegEx

URLs containing at least one of the matching strings will not be crawled.

### Obey robots.txt

If enabled, crawls will respect robots.txt policies. When turned off, robots.txt will be ignored.

### Max pages to process

Limit the number of processed pages

### Max items

Limit the number of extracted items

### Max depth

The maximum depth (number of clicks you need to reach a specific page from the starting URL) that will be allowed to crawl for your site.

### Target Crawl Concurrency

Average number of requests send in parallel to your website.

### Repeat crawl

If enabled, crawl jobs will repeat automatically. Each round will fully re-spider the site from the starting URL, and process pages according to your settings.

### Repeat frequency (in minutes)

The crawl will repeat every x minutes.

### Email notification

You can choose to be notified by email at the conclusion of each crawl.

## Extraction template

The extraction template will help you define the structure of your data. You can add fields to the structure from:

- CSS selectors matching specific elements in the page
- markup vocabularies (JSON-LD or microdata)

### CSS selectors

To add a field to your structure, just click on an element of the page and select the attribute (text, html, src, href, alt...) you want to be used for this field. You can use several attributes for the same element if you want (for example, for an image you can add an 'image' field for the 'src' attribute and a 'caption' field for the 'alt' attribute).

You can also manually edit the CSS selector if you cannot reach an element using the interface.
For each field, the following propertiers are available:

- Field name (mandatory)
- Format (for 'text' attributes only): 'text' or 'date'. If 'date', the value will be converted to a timestamp
- Required: if checked, items without this field won't be scraped
- Schema.org output property: select the corresponding property for the generated JSON-LD markup (see [SEO](/docs/guides/seo) guide)

Once added, a field can not be modified: you must delete it and add it all over again.

### Markup vocabularies

If the page you choose as a template contains JSON-LD or microdata markup, a button labelled 'Add a field from markup' will let you add a field based on one of these properties often used for Article items:

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

As for fields based on CSS selectors, you must give it a name and you can select a schema.org output property if you want this field to be used for the generated JSON-LD markup (see [SEO](/docs/guides/seo) guide).

## Manage list queries

If you want to display article lists on your AMP site that perfectly match the corresponding list on your source site, you can manage list queries.

Such a list query is defined by:

- the name of your choice
- the page URL from the source site
- the CSS selector that matches the div tag surrounding the list of articles on this page

Once you have defined a list query, you can use it for any of your AMP sites in the [Query Builder](/docs/guides/querybuilder). To mimic the list of your source site, you just have to apply a filter (yourQueryListName_tag = TRUE) and a sort property (order by: yourQueryListName_order, direction: Ascendant) on your query.

## Other actions

For each site source, the following actions are available:

### Run/Stop

To run/stop the crawl manually.

### Crawl specific URLs

If you want an item to be extracted without having to wait for the next round, you can crawl specific URLs.

### Delete data

To delete all the items already extracted. The settings of your source and the extraction template are unaffected.

### Delete source

To delete the whole source (items, settings, extraction template).
