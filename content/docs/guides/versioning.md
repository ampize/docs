---
$title@: Versioning
$order: 8
isDraft: 0
$date: 2017-08-07
$dates:
  published: 2017-08-07
description: >

href: /docs/guides/versioning
---

You can benefit from the versioning system of git by plugging your site with a github repository (only compatible with github for now).

## Github settings

To configure the github repository you need to go in « Site Settings » then in « Github » tab.

<amp-img class="col-12 md-col-8" src="/static/img/github-settings.png"  width="925"  height="571"  layout="responsive"  alt="github settings"></amp-img>

### Parameters

There are 4 parameters:

 * Repository URL : your github repository URL (can be with ".git" or not). e.g: "https://github.com/ampize/git-sample" or "https://github.com/ampize/git-sample.git". Please note that this repository must not be empty when you push to github for the fist time (it should contain at least a simple README.md file for example)
 * Token : a github token with write/read access to your repository (see below «How to create a github token»)
 * Branch : "master" by default, this is the main branch which will be synchronized with your site
 * Automatically push when publishing site : when this parameter is checked, each time you will publish your site, AMPize will ask you if you want to push it to github

## Pushing your site to github

Once your github repository is configured, you can push your site to github.

In the site-builder, just on the left of your site's name, select the menu as you would access for the site settings. An entry «Push to Github» should now be there :

<amp-img class="col-6 md-col-3" src="/static/img/github-open-menu.png"  width="238"  height="135"  layout="responsive"  alt="open menu"></amp-img>


<amp-img class="col-12 md-col-8" src="/static/img/github-entry.png"  width="696"  height="396"  layout="responsive"  alt="github entry"></amp-img>

This will push your site to github. All the configuration of your site will be synchronized :

 * Site settings
 * Page settings with your components
 * Each component settings

The process is :

 1. A new branch is created
 2. each file is commited
 3. a Pull Request is created
 4. the PR is merged

Thanks to this process you can easily find each modification in one Pull Request and revert it.

## Pulling your site from github

Below «Push to Github» you can find «Pull from Github». This action will pull and erase all the configuration of your "staging" site by the versioned one.

Note that this will not publish your site, but all the configuration that has not been published will be lost.

## How to create a github token

This is an example of how to create a github token.

Connect to an account which has access to the github repository that you want to synchronize with AMPize. Ideally, this account only have access to this repository because github does not give access per repository but for all the account.

Go to https://github.com/settings/tokens and on the top right click on «Generate new token»

<amp-img class="col-12 md-col-8" src="/static/img/github-token.png"  width="1058"  height="786"  layout="responsive"  alt="github token"></amp-img>

Then select all "repo" in «Select scopes»

<amp-img class="col-12 md-col-8" src="/static/img/github-scope.png"  width="894"  height="497"  layout="responsive"  alt="github scopes"></amp-img>

Then generate the token and copy paste it to AMPize
