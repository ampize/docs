---
$title@: Building Sites
$order: 5
isDraft: 1
$date: 2017-03-17
$dates:
  published: 2017-03-17
description: >

href: /docs/guides/sitebuilder
---
## Overview
The site builder allows you to control every single aspect of your website. It handles anything form the general settings of the entire website to the fine tuning the options of a specific component on one of your pages

Let's take a look at the interface :
<amp-img src="/static/img/site-builder/interface.png"  width="1362"  height="418"  layout="responsive"  alt="site builder interface"></amp-img>

It is comprised of two panels : the main panel made up of the toolbar and the page editor and the side panel.

The toolbar in the main panel houses the following features from left to right :

* The site menu providing access to the following features for the current site : site settings, the centralized template editing interface, the live view button which opens up the current live version of your website (only visible if the website has been published), publishing tools and Github sync tools (if a repository has been configured in site settings) </li>
* The current website and current page separated by a chevron. Clicking on either of them can be used to edit the corresponding name</li>
* The preview button which launches a preview of the current page.</li>
* The page settings button which opens the settings interface for the current page</li>

The page editor allows you to edit the general layout of the page by dragging and dropping components as well as resizing them and editing their individual options.
The side panel has two tabs : a "components" tab containing an accordion list of components to add to the current page and a "pages" tab containing the editable page tree.

## Managing the page tree

<amp-img class="col-6 md-col-3" src="/static/img/site-builder/tree.png"  width="336"  height="392"  layout="responsive"  alt="page tree"></amp-img>

The page tree can be easily managed by drag and drop. Each page has an icon in order to distinguish the homepage, top-level pages and subpages. Moving the pages up and down changes their order in menus. Moving them left an right changes their hierarchy. Simply click on a pages name to select it in the main panel.

Adding a new page is simple : simply click on the plus button at the bottom of the list in order to add a new top-level page and then move it to the desired place in the tree. You can also add a page directly as a child of a specific page using the right-side menu of that page (appears when hovering above page in tree). This menu can also be used to rename and delete pages.

Any top-level page can be set to be the homepage from the right-side menu. The current homepage cannot be deleted. When you first open a website in the site builder it wil already have an empty homepage

## Page and site settings


## Page layout

The page editor is basically an editable representation of the responsive grid of your page. It is a standard 12 column grid. When you drag, drop or resize a component, it will automatically snap to the grid. This means that component width will always be in number of columns and a row cannot have more than 12 columns : overflow will simply jump to the next line.

Whenever you click on a component in the "components" tab of the side panel it is added to your page with its default settings. The new component wil appear at the bottom of the page and will take up an entire line. You can then resize it to the desired number of columns and drag it in the desired position. If there is another component in the way it will automatically move over.

That's the basis of page layout. With this simple and intuitive method you can build any responsive grid-based layout. There are however a few special cases :

* The "Menu" and "User notification" components won't be rendered within the grid as they are floating components. This means that if they were placed in a specific place in the page editor they will automatically leave that place and move to the top of the page on render. As this can potentially disrupt the layout of the line in which tey were it is best to place them alone in a full line either at the top or bottom of the page editor.
* Components can also be resized vertically. This is used to create more complex layouts as it considers any components within the height range of that component as being on the same line wth it. The most basic use case fo this is having 3 components stacked in the center of the page with a component on the side that runs for several lines (or even the whole page) : simply add the side component, stretch it for 3 lines and the desired column width and set it on the right of the page, add the 3 components to its left having one line each.

## Component settings

Depending on its type, each component has a variety of settings. When your mouse hovers over a component a toolbar with different tools becomes visible. It always contains at least a name editor, a deletor and a settings tool. The first two are self-explanatory. The settings tool is used to configure basic settings such as text and number fields, page links, image links, checkboxes, component layout, etc. It is by far the most common tool for configuring components. Some settings however are more complex and require special editing tools.

Specialized tools handle settings that a simple form cannot such as rich text, HTML code, and datasource queries and templates. The rich text editor displays a full-screen WYSIWYG editor in which the CSS code of your website and current page are automatically applied in order to make the preview as close as possible to the rendered result. The HTML editor works in a similar way but uses a raw HTML editor instead of a WYSIWYG editor. In both cases the resulting HTML will be automatically converted to valid AMP HTML on render. This means you don't have to worry about learning AMP in order to use these editors : rich text or HTML editing skills will do just fine.

Components that display content form your datasources such as lists, details and carousels also have query and template settings. Both are handled by the query builder tool. I displays a wizzard with three steps : building your query, choosing a custom template or an existing one and fiannly result preview/custom template editing. The last step also uses the CSS code of your website and current page in ordedr to ensure the preview is as close as possible to th rendered result. Once these settings are completeand if you chose to use a custom template, the component will also display a template tool wich alows direct access to the last stage of this wizard in edit mode for convenience.

Because of the highly specific nature of its settings, components that use the query builder tool require configuration before they can be rendered unlike the majority of components which come with valid default settings.

## Preview

The page preview shows what the current page looks like on mobile, tablet or desktop. This shows the page using the settings currently in your editor and not the published version of the page so it is a very useful tool to test the effects of your changes before publishing them.

You can also open the preview in a new window (one of the size adjustment buttons in the preview). This can be useful in a dual screen configuration with editor on one side and result on the other.
