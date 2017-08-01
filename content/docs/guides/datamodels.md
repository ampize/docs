---
$title@: Custom Data models
$order: 99
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/datamodels
---
AMPize uses its own data framework called Alambic to connect heterogeneous data sources. The core system is based on Facebook GraphQL and relies on a declarative and strong-types data model, which describes the types of objects that can be returned, the relations between them and the queries endpoints.

<br>

## Models

<br>

A basic data model configuration describes:

* the data structure: Types
* how data can be fetched: Connectors

## Built in Connectors Types

<br>

AMPize.me currently supports three different types of connector, also know as data sources:

* Websites
* Databases
* REST API's

More connectors will be added in the future, including specific API's, such as Magento API for example.

<br>

## Types

<br>

At the heart of any GraphQL implementation is a description of what types of objects it can return, described in a GraphQL type system and returned in the GraphQL Schema.

<br>

The Alambic type system extends the GraphQL initial format by adding information about data validation and relations between objects.

<br>

### Internal Object Types

<br>
Alambic provides several internal types that can be used to compose your own custom type definition:
<br><br>

| Internal Type | Description |
|----------|------|
| String | String |
| Int | Integer |
| Float | Float |
| Boolean | Boolean, TRUE or FALSE |
| ID | String or numeric |
| ImageUrl | Image url |
| Date | Date format |
| DateTime | Datetime format |
| Time | Tme format |
| HTML | HTML, will automatically be converted to AMP HTML|
| JSON | JSON data|
| JSONArray | JSON array data |

<br>

### Custom Object Types

<br>

Every object field that compose your custom Type must belongs to one of internal or custom types:


```json
{
  "Product": {
    "name": "Product",
    "description": "A product type",
    "fields": {
      "productId": {
        "type": "ID",
        ...
      },
      "Name": {
        "type": "String",
        ...      
      },
      "Price": {
        "type": "Float",
        ...      
      },
      "Weight": {
        "type": "Int",
        ...      
      },
      "InStock": {
        "type": "Boolean",
        ...      
      },
      "Stores": {
        "type": "Store",
        ...          
      }
    }
  }
}
```

* the key "Product" is the name of the Type, it MUST be unique across all datasources
* the "name" value MUST be equal to the Type key
* each field is described by a number of properties

### Fields

<br>

Fields are part of Object Types definitions.

<br>

They are described by the following options:

<br>

| Property | Type | Required | Description |
|----------|------|-----------------------|----------|
| name | String | No | Name of the field. If not set GraphQL will use the key of fields array |
| type | Type | Yes | Must be an Internal Type or an existing foreign object Type |
| description | String | No | Field description for clients |
| required | Boolean | No | Is this field required? default to false |
| args | Array | No | The args array is usually used to describe the fields that can be retrieved from a foreign object Type |
| relation | Key:Value | No | Describes the relation between the current and the foreign object Type. Key = foreign key name; Value = local key Name. |

<br>

## Relations

<br>

Individual object types are easy to setup, but when building real applications developers will often need to connect objects together and build relations.

<br>

With relational databases, such as MySQL, relations are included in the core system, and querying multiple objects through their relations is easily done through SQL with JOINS statements, sometimes at the expense of performance.

<br>

In NoSQL databases querying multiple, related objects turn out to be more painful as NoSQL do not handle JOINS.

<br>

And when it comes to querying two or more different databases simultaneously, developers usually answer: "No way".

<br>

Fortunately it's a pretty easy task to handle with Alambic.

<br>

You can define the following relations between object types:

* One to One
* One to Many
* Many to Many
* Embedded types

<br>

### One to One

<br>

A one to one relation between object type A and object type B defines that every instance of A "has one" instance of B. For example every "Post" has one "Author".

<br>

The declaring type (Post) has a foreign key property (authorId) that references the primary key (id) of the target type (Author).

<br>
<amp-img src="/static/img/hasOne.png" width="461" height="133" layout="fixed" alt="has many relation"></amp-img>
<br>

```json
{
  "Post": {
    "fields": {
      "id": {...},
      "text": {...},
      "author": {
        "type": "Author",
        "relation": {
          "id": "authorId"
        }    
      }
    }
  }
}
```

The relation is always built as a "key:value" expression where the key is the target type key name and the value is the declaring type key name.

<br>

### One to many

<br>

A one to many relation between object type A and object type B defines that every instance of A "has many" instances of B. For example every "Author" has many "Posts".

<br>

The target type (Post) has a foreign key property that references the primary key of the declaring type (Author).

<br>

<amp-img src="/static/img/hasMany.png" width="460" height="133" layout="fixed" alt="has many relation"></amp-img>

<br>
The only difference between one-to-one and one-to-many declarations is that the "multivalued" option is set to true for one-to-many.

```json
{
  "Author": {
    "fields": {
      "id": {...},
      "name": {...},
      "posts": {
        "type": "Post",
        "multivalued": true,
        "relation": {
          "authorId": "id"
        }    
      }
    }
  }
}
```
<br>
### Many to Many
<br>

A many to many relation between two object types can be established through a third type.  

<br>

For example Author and Blog can share many posts.

<br>
<amp-img src="/static/img/manyToMany.png" width="750" height="148" layout="fixed" alt="has many relation"></amp-img>
<br>

```json
{
  "Post": {
    "fields": {
      "id": {...},
      "text": {...},
      "Author": {
        "type": "Author",
        "relation": {
          "id": "authorId"
        }    
      },
      "Blog": {
        "type": "Blog",
        "relation": {
          "id": "blogId"
        }    
      }      
    }
  }
}
```

## Embedded types

<br>

Embedded relations are used to represent a type that embeds another type.

<br>

For example a post embeds one or many comments.

```json
{
  "id": 1,
  "text": "My first blog post on alambic",
  "comments": [
      {"author": "John Doe", "text": "Awesome!"},
      {"author": "Jane Doe", "text": "Very useful"}
  ]
}
```

In Alambic every foreign field type declared without the "relation" property is considered as embedded.

```json
{
  "Comment": {
    "fields": {
      "author": {...},
      "text": {...}
    }
  }
}
```

```json
{
  "Post": {
    "fields": {
      "id": {...},
      "text": {...},
      "comments": {
        "type": "Comment",
        "multivalued": true
        ** no relation **
      }
    }
  }
}
```
