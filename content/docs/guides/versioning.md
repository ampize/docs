---
$title@: Versioning
$order: 6
isDraft: 1
$date: 2014-03-17
$dates:
  published: 2014-03-17
description: >

href: /docs/guides/versioning
---

You can benefit from the versionning system of git by plugging your site with a github repository (only compatible with github for now).

<br>

##Github settings
<br>
To configure the github repository you need to go in « Site Settings » then in « Github » tab.

<div class="col-12 md-col-8">
	<amp-img src="/static/img/github-settings.png"  width="925"  height="571"  layout="responsive"  alt="github settings"></amp-img>
</div>

###Parameters
There is 4 parameters :

 * Repository URL : your github repository URL (can be with ".git" or not). e.g: "https://github.com/ampize/git-sample" or "https://github.com/ampize/git-sample.git"
 * Token : a github token with write/read access to your repository (see below «How to create a github token»)
 * Branch : "master" by default, this is the main branch which will be synchronized with your site
 * Automatically push when publishing site : when this parameter is checked, each time you will publish your site, ampize will ask you if you want to push it to github

##Pushing your site to github
<br>
Once your github repository configured, you can push your site to github.

In the site-builder, just on the left of your site's name, access to the menu like you would access to the site settings. An entry «Push to Github» should now be there :

<div class="col-6 md-col-3">
	<amp-img src="/static/img/github-open-menu.png"  width="238"  height="135"  layout="responsive"  alt="open menu"></amp-img>
</div>
<div class="col-12 md-col-8">
	<amp-img src="/static/img/github-entry.png"  width="696"  height="396"  layout="responsive"  alt="github entry"></amp-img>
</div>

<br>
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

<br>
##Pulling your site from github
<br>
Below «Push to Github» you can find «Pull from Github». This action will pull and erase all the configuration of your "staging" site by the versioned one.

Note that this will not publish your site, but all the configuration that has not been published will be lost. 

<br>

##How to create a github token
<br>
This is an example of how to create a github token.

Connect to an account which has access to the github repository that you want to synchronize with ampize. Ideally, this account only have access to this repository because github does not give access per repository but for all the account.

Go to https://github.com/settings/tokens and on the top right click on «Generate new token»

<br>
<div class="col-12 md-col-8">
	<amp-img src="/static/img/github-token.png"  width="1058"  height="786"  layout="responsive"  alt="github token"></amp-img>
</div>


Then select all "repo" in «Select scopes»

<br>
<div class="col-12 md-col-8">
	<amp-img src="/static/img/github-scope.png"  width="894"  height="497"  layout="responsive"  alt="github scopes"></amp-img>
</div>
Then generate the token and copy paste it to ampize