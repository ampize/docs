---
$title@: Advanced Queries
$order: 5
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/querybuilder
---
<h2 class="mt4 mb4">Overview</h2>
<p>The Query Builder is a graphical interface that lets you define queries based on your datasources' structures. You will use it on several AMPize components: list, detail, carousel, slides...</p>
<p>The left column shows all the structures (or Types) defined in your datamodels. The larger space on the right side contains the structures you have added to your query.</p>
<p>To add a Type to your query, just click on its name on the left column. Structures in this left column are now filtered and only the Types that are linked to the one you have just selected are visible. You can add other Types to the query, by clicking on their name in the left column.</p>
<p>For each of the selected Types, you can choose the fields you want to be returned by the query, by checking the box next to the field name.</p>
<h2 class="mt4 mb4">Focus on filters, sort, ...</h2>
<p>Thanks to the 'filter' icon, you can add:</p>

- Filters: select a field, an operator and fill in a value. The results will be filtered according to this criteria. If you add several filters, you can choose if you want these filters to be joined by an 'AND' or 'OR' operator.
- Sort: you can add an 'order by' criteria on a field and a direction (ascendant/descendant)
- Group: you can add a 'group by' condition (on database sources only)

<h3 class="mb3 mt3">How to retrieve GET parameters from URL?</h3>
<p>You can retrieve a GET parameter and use it as a value in a filter by using this syntax: ___paramName___</p>
<p>When you add a filter in the Query Builder for a Type from a Site source, you can click on the 'Value from URL' icon to automatically insert the right variable.</p>
<h3 class="mb3 mt3">How to filter/order a list the same way as on a crawled website? (site sources only)</h3>
<p>You can use List queries to achieve this.</p>
<p>First, you have to define your list on the source site (see <a href="/docs/guides/crawl">Plugging a website</a>).</p>
<p>You are now able to apply a specific filter and a sort property on your query based on this list. For example, if you named this list 'home', a specific filter name 'home_tag' is now available (just add a filter 'home_tag = TRUE'), and a specific sort property as well (just add order by: home_order, direction: Ascendant to mimic the source list).</p>
