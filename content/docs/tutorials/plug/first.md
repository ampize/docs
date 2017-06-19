---
$title@: First request
$order: 1
---
This tutorial will show you how to plug a REST API data-source.

1. In the hamburger menu, click on the "Data sources" entry
2. Create a new REST API and name it "test"
3. Fill in the common base URL to all API's endpoints: [http://content.guardianapis.com](http://content.guardianapis.com)

<amp-img src="/static/img/plug_first.png" width="899"height="450" layout="responsive">  

Now we'll set a few more parameters specific to the Guardian API:

- the query param "show-fields" is used to get the detailed article fields
- the query-param "show-tags" to get the article tags.

<amp-img src="/static/img/plug_query.png" width="897"height="583" layout="responsive">  

This API also needs a key in the http header.

<amp-img src="/static/img/plug_header.png" width="899"height="491" layout="responsive">  

The last step is to describe the API data model through a JSON file that we can upload or feed inline.

This file basically describes how to get data (API endpoints and parameters) and the response we get.

Here we can see 4 endpoints: 'Contents', ‘Fields’, ‘Tags’ and ‘Sections’.


We just have to click on ‘Create data source’ and we're done.


This source is now ready to feed our AMP components.

Let's have a look at the results of a simple graphQL query based on this data source.

[sourcecode:text]
{
    "content": {
        "name": "content",
        "description": "The Guardian API content",
        "fields": {
            "id": {
                "type": "String",
                "required": true,
                "description": "Content ID"
            }
        },
        "expose": true,
        "multiEndpoint": {
            "name": "contents",
            "args": {
            }
        },
        "singleEndpoint": {
            "name": "content",
            "args": {
            }
        },
        "connector": {
            "type": "test",
            "configs": {
                "segment": "search",
                "resultsPath": "response.results"
            }
        }
    }
}
[/sourcecode]


<p class="white"><a class="ampstart-btn right" href="/docs/tutorials/plug/fields">Continue to Step 2</a></p>
