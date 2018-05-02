---
$title@: Plugging a REST API
$order: 1
isDraft: 0
$date: 2017-08-31
$dates:
  published: 2017-08-31
description: >

href: /docs/guides/restapi
---
Plugging your REST API is quite easy and shouldn't take more than a few minutes.

## Source

To connect a REST API, you must first give a name to this source and define the API base URL (common base URL to all API endpoints).

## Params

### Basic auth params

User / password to connect to the API.

### Query param

You can add as many API Query parameters as you need.

### HTTP headers

You can add as many API HTTP headers as you need.

## Data model

Your source must be represented by its data model: it is a basic JSON configuration to describe the data structure (Types: objects and relations between these objects) and how data can be fetched (Connectors). See [Data Models](/docs/guides/datamodels) guide for more info.
