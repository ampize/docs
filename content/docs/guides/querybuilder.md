---
$title@: Advanced Queries
$order: 5
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
description: >

href: /docs/guides/querybuilder
---
## Overview

The Query Builder is a graphical interface that lets you define queries based on your data sources. You will use it on every AMPize component that need to be fed by data: list, detail, carousel, slides...

The left column shows all the structures (or Types) defined in your data models. The larger space on the right side contains the structures you have added to your query.

To add a Type to your query, just click on its name on the left column. Structures in this left column are now filtered and only the Types that are linked to the one you have just selected are visible. You can add other Types to the query, by clicking on their name in the left column.

For each of the selected Types, you can choose the fields you want to be returned by the query, by checking the box next to the field name.

## Focus on filters, sort, ...

Thanks to the 'filter' icon, you can add:

- **Filters**: select a field, an operator and fill in a value. The results will be filtered according to this criteria. If you add several filters, you can choose if you want these filters to be joined by an 'AND' or 'OR' operator.
- **Sort**: you can add an 'order by' criteria on a field and a direction (ascendant/descendant)
- **Group**: you can add a 'group by' condition (on database sources only)

### How to retrieve GET parameters from URL?

You can retrieve a GET parameter and use it as a value in a filter by using this syntax: ___paramName___

When you add a filter in the Query Builder for a Type from a Site source, you can click on the 'Value from URL' icon to automatically insert the right variable.

### How to filter/order a list the same way as on a crawled website? (site sources only)

You can use List queries to achieve this.

First, you have to define your list on the source site (see [Plugging a website](/docs/guides/crawl)).

You are now able to apply a specific filter and a sort property on your query based on this list. For example, if you named this list 'home', a specific filter name 'home_tag' is now available (just add a filter 'home_tag = TRUE'), and a specific sort property as well (just add order by: home_order, direction: Ascendant to mimic the source list).
