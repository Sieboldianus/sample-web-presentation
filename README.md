How to setup your new VGIscience presentation
=============================================

To create a new presentation:

1. Fork this project by selecting the `Fork` button below the project headline on this page.
2. Select your user name or the group, which the website is for.
3. In the new project, select `Settings` in the top-level navigation and
    1. remove or change the project description
    2. scroll down to `Rename repository` and rename both name and path
    
    The website will automatically be accessible under a subdomain of `namespace.vgiscience.org`. The namespace is defined by your username or the group name you created this project under. [Read about some practical examples before choosing a project name](https://gitlab.vgiscience.de/help/user/project/pages/getting_started_part_one.md#practical-examples). Gitlab Pages is already enabled for this project. The corresponding Pages wildcard domain is `*.vgiscience.org`.

4. Go to the file repository (select `Repository` in the top-level navigation) and edit at least the `baseurl` setting in the file [_config.yml](_config.yml) to `/YOUR-PROJECT-NAME` (click the file name in the list, the `edit` button then is on the right next to the red `delete` button). You may also edit the title, email and description settings. Do not edit anything below `# Build settings`! Hit `Commit changes` to save your edit. With this commit you have just triggered the first build process of your new website.
5. Wait a minute for the build process to pass and head over to your new website at `https://YOUR-USER-OR-GROUPNAME.vgiscience.org/YOUR-PROJECT-NAME`
6. If this is the first website for your user- or group name, get in touch with @ml to get a valid SSL certificate for your new subdomain, while [this issue](https://gitlab.com/gitlab-org/gitlab-ce/issues/28996) is not resolved.

You may delete this file from the repository (red `delete` button), if you want to. It is not being rendered into the website, until you add a frontmatter to it.


Creating pages
--------------

Create more pages by adding files with the `+` button. Name them as you want them to appear in the URL: `example.md` will be rendered to `https://…vgiscience.org/…/example.html`

Always create the *frontmatter* first. Add the following to the top of the new file:
```markdown
---
layout: page
title: YOUR TITLE
---
```
Add content to the page using Markdown syntax. [Read the help page for Markdown Syntax](https://gitlab.vgiscience.de/help/user/markdown.md) (it's very easy!)

Creating blog posts
----------

Create news or blog posts by adding files to the `_posts` directory according to the example post. If you do not want to have blog functionality on your website, change the layout of `index.md` in its frontmatter to `page` and add any content to it instead.

External links
--------------

To add links to external pages to the page menu, create a page and set this frontmatter:
```markdown
---
layout: redirect
link: https://example.com
title: YOUR TITLE
---
```

Alternative menu entries
------------------------
If your page title is too long for the menu or you want to name the entry other than the actual page title, add `menu: YOUR MENU TITLE` to the frontmatter.

Bibsonomy integration
---------------------

If you want to add a publication list, you can have Jekyll create one for you using your [Bibsonomy](https://www.bibsonomy.org) account as a source. Add your credentials to `_config.yml` and place the following snippet to the file, within which you want your publication list appear:

    {% bibsonomy user yourusername yourtags 999 %}

Change `yourusername` to your actual Bibsonomy user name and `yourtags` to a space-separated list of tags, whose publications you want to have in the list. For further information see the [plugin page](https://github.com/rjoberon/bibsonomy-jekyll). The last number is the maximum number of publications that should be listed.
