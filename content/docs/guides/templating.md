---
$title@: Templating
$order: 6
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/templating
---
<p>AMPize uses Mustache templates to display content from your data sources. Every query-based component (list, detail, carousel) uses them. Together with the CSS code fields in page and site settings they are the main tools to customize the design of your AMPize website</p>
<h2 class="mt4 mb4">Overview</h2>
<p>Mustache templates are simple and easy to use. Being logic-less, they don't have any advanced features such as conditionals and yet they can cover the vast majority of use cases. This makes Mustache very easy to learn.</p>
<p>AMPize automatically generates basic templates for every use case directly in the query builder so you never need to start from scratch. This makes templating productive as most of the time you can either leave the auto-generated templates as they are ord do some minor tinkering. You can also save your templates and reuse them in other components of the same type and perform centralized updates.</p> 
<h2 class="mt4 mb4">Template management</h2>
<p>Whenever you use the query builder, the last stage is always a preview of the resulting html. By default, the query builder automatically generates a template adapted to your use case (list, detail or carousel) and uses it to render the preview. This default template lists all the fields from your query in their order of definition. While it may do the job for simple lists of titles or basic content details it might need some tinkering if you want to change the order in which fields are displayed or modify their layout.</p>
<p>Clicking on the pencil-shaped edit button will split the query builder window into two panels : the code editor and the preview. In order to help you code, every change you make in the editor immediately affects the preview. We will cover the details of editing in the next section of this guide. </p>
<p>If at some point during your editing you realize that a field is useless or that you need other fields that aren't in the query you can always go back to the first stage and make the necessary changes. The template will not be re-generated as you return to the last stage unless you click the corresponding button in the second stage.</p>

