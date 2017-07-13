---
$title@: Plugging a Database
$order: 3
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/database
---
<p>Plugging your database is quite easy and shouldn't take more than a few minutes.</p>
<h2 class="mt4 mb4">Connection to your database</h2>
<p>To connect a database, you must give a name to this source, select the DB Engine type (PDO MySQL / MySQLi) and define the usual connection settings (host, port, user, password, schemaDB).</p>
<h2 class="mt4 mb4">Data model</h2>
<p>You source must be represented by its data model: it is a basic JSON configuration to describe the data structure (Types: objects and relations between these objects) and how data can be fetched (Connectors).</p>
<p>You can either upload your own JSON model, or click on 'Build model form DB' to automatically generate the model. It's just magic.</p>
