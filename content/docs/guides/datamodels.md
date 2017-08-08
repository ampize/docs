---
$title@: Custom Data models
$order: 99
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
components:
  - gist
description: >

href: /docs/guides/datamodels
---
AMPize uses its own data framework called Alambic to connect and query heterogeneous data sources. Alambic is based on Facebook GraphQL and relies on a declarative and strong-types data model, which describes the types of objects that can be returned, the relations between them and the queries endpoints.

## Models

A basic data model configuration describes:

* the data structure: Types
* how data can be fetched: Connectors

## Built in Connectors

AMPize.me currently supports three different types of connectors, also know as data sources:

* Websites
* Databases
* REST API's

More connectors will be added in the future, including product specific API's, such as Magento API for example.

Types are described through Json files that can be uploaded in AMPize during the configuration process of REST API's and databases data sources.

Let's take a dive into this JSON configuration.

## Types

At the heart of any GraphQL implementation is a description of what types of objects it can return, described in a GraphQL Type system and returned in the GraphQL Schema.

The Alambic Type system extends the GraphQL initial format by adding information about data validation and relations between objects, along with new internal Types, such as ImageUrl, Date, ... these internal Types that can be used to compose your own custom Type definition.

### Internal Object Types

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

### Custom Object Types

Every object field that compose your custom Type must belongs to one of internal or custom Types:

```json
{
  "Product": {
    "name": "Product",
    "description": "A product Type",
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

## Fields

Fields are part of Object Types definitions.

They are described by the following properties:

| Property | Type | Required | Description |
|----------|------|-----------------------|----------|
| name | String | No | Name of the field. If not set GraphQL will use the key of fields array |
| type | Type | Yes | Must be an Internal Type or an existing foreign or embedded object Type |
| description | String | No | Field description for clients |
| required | Boolean | No | Is this field required? default to false |
| args | Array | No | The args array is usually used to describe the fields that can be retrieved from a foreign object Type |
| relation | Key:Value | No | Describes the relation between the current and the foreign object Type.<br> Key = foreign key name; Value = local key Name. |

## Relations

Individual object Types are easy to setup, but when building real applications developers will often need to connect objects together and build relations.

You can define the following relations between object Types:

* One to One
* One to Many
* Many to Many
* Embedded Types

### One to One

A one to one relation between object Type A and object Type B defines that every instance of A "has one" instance of B. For example every "Post" has one "Author".

The declaring Type (Post) has a foreign key property (authorId) that references the primary key (id) of the target Type (Author).

<amp-img class="col-12 md-col-5" src="/static/img/hasOne.png" width="461" height="133" layout="responsive" alt="has many relation"></amp-img>

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

The relation is always built as a "key:value" expression where the key is the target Type key name and the value is the declaring Type key name.

### One to many

A one to many relation between object Type A and object Type B defines that every instance of A "has many" instances of B. For example every "Author" has many "Posts".

The target Type (Post) has a foreign key property that references the primary key of the declaring Type (Author).

<amp-img class="col-12 md-col-5" src="/static/img/hasMany.png" width="460" height="133" layout="responsive" alt="has many relation"></amp-img>

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

### Many to Many

A many to many relation between two object Types can be established through a third Type.  

For example Author and Blog can share many posts.

<amp-img class="col-12 md-col-5" src="/static/img/manyToMany.png" width="750" height="148" layout="responsive" alt="has many relation"></amp-img>

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

### Embedded Types

Embedded relations are used to represent a Type that embeds another Type.

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

In Alambic every foreign field Type declared without the "relation" property is considered as embedded.

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

## Connectors settings

Once you described the data structure (Types, fields) and the relations between Types, you'll need to set up a few more more attributes in your model to specify how to fetch data from the original source.

| Attribute | Description |
|----------|------|
| expose | Boolean, usually true if this Type can be directly queried |
| singleEndpoint | Describes the API endpoint used to retrieve one item |
| multiEndpoint | Describes the API endpoint used to retrieve a list of items |
| connector | Describes the connector settings specific to this Type |

The configuration can be slightly different depending on the source Type: Database or REST API.

### REST API settings

```json
{
    "content": {
        "name": "content",
        "description": "The Guardian API content",
        "fields": {
            "id": {...},
            ...
        },
        "expose": true,
        "multiEndpoint": {
            "name": "contents",
            "args": {
                "q": {
                    "type": "String"
                }
            }
        },
        "singleEndpoint": {
            "name": "content",
            "args": {
                "ids": {
                    "type": "String",
                    "required": true,
                    "modelField": "id",
                    "description": "Content ID"
                }
            }
        },
        "connector": {
            "type": "guardian",
            "configs": {
                "segment": "search",
                "resultsPath": "response.results",
                "startFieldName": "page",
                "limitFieldName": "page-size",
                "orderByFieldName": "order-by"
            }
        }
    }
}
```
In this configuration:

* a "content" object can be retrieved one at a time by passing a required "ids" string parameter to the API. This parameter is mapped to the "id" field.

```json
    "singleEndpoint": {
        "name": "content",
        "args": {
            "ids": {
                "type": "String",
                "required": true,
                "modelField": "id",
                "description": "Content ID"
            }
        }
    }
```

* a list of "contents" can be also be retrieved by passing a "q" string argument to the API.

```json
    "multiEndpoint": {
        "name": "contents",
        "args": {
            "q": {
                "type": "String"
            }
        }
    }
```

The connector configuration is done through the following properties:

```json
    "connector": {
        "type": "guardian",
        "configs": {
            "segment": "search",
            "resultsPath": "response.results",
            "detailResultsPath": "response.results.0",
            "startFieldName": "page",
            "limitFieldName": "page-size",
            "orderByFieldName": "order-by",
            "orderByDirectionFieldName": "order-direction",
            "ascendantValue": "ASC",
            "descendantValue": "DESC"
        }
    }
```

* the "type" value must be the name given to the data source
* the "segment" value is concatenated with the to base API url of the data source
* the segment can accept vars substitution from the endpoint arguments with the syntax "{argName}"
* the API response is expected to yield results in the "response.results" path
* the single endpoint is expected to yield results as the first item of the "response.results" list
* pagination can be triggered by passing the "page" (start) and "page-size" (limit) arguments
* the order of the results can be set by passing the "order-by" argument
* the sort direction can be set by passing the "order-direction" argument
* Ascendant sort direction is set to "ASC"
* Descendant sort direction is set to "DESC"

Beware that:

- depending on your API, pagination and sorting may not be available
- Ascendant and Descendant values may be omitted if they match the default values: "ASC" and "DESC"

### Database settings

In AMPize.me the database model is automatically generated from the database schema.
A Type is generated from each table.

```json
{
    "user": {
        "name": "user",
        "description": "My user table in MySQL",
        "fields": {
            "id": {...},
            ...
        },
        "expose": true,
        "multiEndpoint": {
            "name": "user_multi",
            "args": {}
        },
        "singleEndpoint": {
            "name": "user_single"
        },
        "connector": {
            "type": "myDBDataSource",
            "configs": {
                "table": "user"
            }
        }
    }
}
```

* the multi endpoint is named {typeName} + "_multi" by default, but you set your own name
* the single endpoint is named {typeName} + "_single" by default, but you set your own name
* you don't need to set any arguments for endpoints, they will be automatically injected in the model, based on the table fields
* the connector config only takes a "table" attribute that maps the type to a db table

## Examples

These files are used in AMPize samples:

* [REST API Sample Model for the Guardian API](https://gist.github.com/dfanchon/a1d6f1a358767008797de8ab2b4e51d3)
<amp-gist
    data-gistid="a1d6f1a358767008797de8ab2b4e51d3"
    layout="fixed-height"
    height="50">
</amp-gist>
<br>
* [DB Sample Model for MySQL Sakila database](https://gist.github.com/dfanchon/89986c8637606f650a5558bbc22e7975)
<amp-gist
    data-gistid="89986c8637606f650a5558bbc22e7975"
    layout="fixed-height"
    height="50">
</amp-gist>
