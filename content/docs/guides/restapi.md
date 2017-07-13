---
$title@: Plugging a REST API
$order: 1
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/restapi
---
<p>Plugging your REST API is quite easy and shouldn't take more than a few minutes.</p>
<h2 class="mt4 mb4">Source</h2>
<p>To connect a REST API, you must first give a name to this source and define the API base URL (common base URL to all API endpoints).</p>
<h2 class="mt4 mb4">Params</h2>
<h3 class="mb3 mt3">Basic auth params</h3>
<p>User / password to connect to the API.</p>
<h3 class="mb3 mt3">Query param</h3>
<p>You can add as many API Query parameters as you need.</p>
<h3 class="mb3 mt3">HTTP headers</h3>
<p>You can add as many API HTTP headers as you need.</p>
<h2 class="mt4 mb4">Data model</h2>
<p>You source must be represented by its data model: it is a basic JSON configuration to describe the data structure (Types: objects and relations between these objects) and how data can be fetched (Connectors). See <a href="docs/guides/datamodels">Data Models<a> guide for more info.</p>
