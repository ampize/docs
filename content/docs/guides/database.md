---
$title@: Plugging a Database
$order: 3
isDraft: 0
$date: 2014-08-07
$dates:
  published: 2014-08-07
description: >

href: /docs/guides/database
---
Plugging your database is quite easy and shouldn't take more than a few minutes.

## Connection to your database

To connect a database, you must give a name to this source, select the DB Engine type (PDO MySQL / MySQLi) and define the usual connection settings (host, port, user, password, schemaDB).

## Data model

You source must be represented by its data model: it is a basic JSON configuration to describe the data structure (Types: objects and relations between these objects) and how data can be fetched (Connectors).

See the [Data Models](/docs/guides/datamodels) guide for more info.

You can either upload your own JSON model, or click on 'Build model form DB' to automatically generate the model.

It's just magic.
