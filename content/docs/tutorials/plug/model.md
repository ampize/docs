---
$title@: Model
$order: 3
components:
  - gist
---
The last step is to describe the API data model through a JSON file which you can either upload or copy & paste in the black square.

<amp-img src="/static/img/plug_model_0.png" width="898"height="721" layout="responsive" class="screenshot">  

The JSON file describes how to get data (API endpoints and parameters) and the response you will get. For example, you will find below the JSON file for the Guardian API. 

<amp-gist
    data-gistid="a1d6f1a358767008797de8ab2b4e51d3"
    layout="fixed-height"
    height="225">
</amp-gist>
<p class="mt4">
The article structure is described through these 4 graphQL types: 'content', ‘field’, ‘tag’ and ‘section’.

<amp-img src="/static/img/theguardian.jpg" width="768"height="480" layout="responsive" class="screenshot">  

That's it! Select ‘Create data source’ and you're done. This source is now ready to feed your AMP components.

</p>
<p class="white"><a class="btn right" href="/docs/tutorials/create">Next Tutorial: create your site</a></p>
