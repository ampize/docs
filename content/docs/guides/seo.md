---
$title@: SEO
$order: 10
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
description: >

href: /docs/guides/seo
---
## Allow bot indexing

By default, AMPize.me prevent new sites from being indexed indexed by search engines with a 'noindex,nofollow' meta tag.

To authorize bot indexing, just enable the 'Allow bot indexing' property in the Site Settings (SEO tab).

## Meta tags

Meta tags provide information about the web page and are used by search engines to help categorize the page correctly.

AMPize.me allows you to specify the following SEO attributes:

- Title
- Description
- Keywords

These attributes can be specified in the Site Settings (SEO tab) and overridden for each page in the Page Settings (SEO tabs).

To add keywords, just press enter after each keyword.

## Structured data

AMP pages that have structured data can appear in the Top stories carousel in search results. Without structured data, AMP pages can appear only as standard blue links in Google Search results.

AMPize.me will add a structured data element (JSON-LD markup) describing the current article in each page containing a 'Content Detail' component. This markup provides the following properties:

- **type**: schema.org type. Must be configured in the data source. For a 'Site' source, select the correct 'Schema.org Type' in the first step ('Source'). Can be either NewsArticle, Article or BlogPosting.
- **mainEntityOfPage**: the canonical URL of the article page, determined automatically by AMPize.me
- **headline**: the headline of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'headline' in the 'Schema.org output property' for the field that must be used as headline.
- **image** (URL, height and width): the representative image of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'image' in the 'Schema.org output property' for the field that must be used as an image. Beware! Images should be at least 696 pixels wide and in .jpg, .png, or. gif format. You can provide a default image in the Site Settings (SEO tab), that will be used if an article doesn't come with an image.
- **publisher.name**: The name of the publisher. Must be set in the Site Settings (SEO tab).
- **publisher.logo**: The logo of the publisher. Must be provided in the Site Settings (SEO tab). Beware! This logo must be in .jpg, .png, or .gif format, and should fit in a 60x600px rectangle, and either be exactly 60px high (preferred), or exactly 600px wide.
- **datePublished**: The date and time the article was first published. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'datePublished' in the 'Schema.org output property' for the field that must be used as a publication date.
- **dateModified**: The date and time the article was most recently modified. Can be declared in the data model of your data source (recommended, but not required). For a 'Site' source, in your Extraction template, select 'dateModified' in the 'Schema.org output property' for the field that must be used as a modification date.
- **author.name**: The name of the author of the article. Must be declared in the data model of your data source. For a 'Site' source, in your Extraction template, select 'author.name' in the 'Schema.org output property' for the field that must be used as the author name. You can set a default author name in the Site Settings (SEO tab), that will be used if an article doesn't come with an author name.
- **description**: A short description of the article. Can be declared in the data model of your data source (recommended, but not required). For a 'Site' source, in your Extraction template, select 'description' in the 'Schema.org output property' for the field that must be used as a description.

## How to make your AMP pages discoverable?

So that Google can easily find your AMP pages, you should add to your non-AMP pages links to the AMP versions. The easiest way to do this is to include our automated discovery script by adding the following code to the head section of your detail pages : `<script type="text/javascript" src="https://your-ampize-domain.com/ampize.js"></script>`. The exact script link can be found in the site settings tool in the SEO tab right beneath the 'Use original URL as canonical' switch provided that your website has a domain name.
If your AMP website only has one detail page than this link will do : the script will automatically insert the link to the AMP equivalent of your detail page in the head section. However, if you have several detail pages displaying data from several datasources than the script will need an extra hint in order to choose the most appropriate page on which to display the AMP version of your detail : simply add `?model=nameOfYourModelDetail` to the script tag. So if you have a site source called 'content' than the script link will be `<script type="text/javascript" src="https://your-ampize-domain.com/ampize.js?model=contentDetail"></script>`. For other datasource types such as databases and REST APIs simply use the name you gave the singleEndpoint of the desired model.

The head of AMP pages should also contain a link tag, to the related non-AMP version of the page. To do so, you should fill in the 'Canonical URL' field in the Page Settings (SEO tab). Detail pages will automatically include such a tag, provided that you enable the 'Use original URL as canonical' option in the Site Settings (SEO tab).
