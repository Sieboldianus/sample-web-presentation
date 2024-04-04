How to setup your new IOER presentation
=============================================

To create a new presentation:

1. Fork this project by selecting the `Fork` button below the project headline on this page.
2. Select your user name or the group, in which you want to fork the presentation template.
3. In the new project, select `Settings - General` in the left navigation, expand `Advanced settings`, scroll down to `Rename repository` and rename both name and path to your needs, e.g. `/YOUR-NEW-PRESENTATION`

    The presentation will automatically be accessible under a subdomain of `namespace.gp.hrz.tu-chemnitz.de/YOUR-NEW-PRESENTATION`. The namespace is defined by your username or the group name you created this project under. [Read about some practical examples before choosing a project name](https://gitlab.hrz.tu-chemnitz.de/help/user/project/pages/getting_started_part_one.md#practical-examples). Gitlab Pages is already enabled for this project. The corresponding Pages wildcard domain is `*.gp.hrz.tu-chemnitz.de`.

4. Go to the file repository (select `Repository` in the top-level navigation) and edit at least the `baseurl` setting in the file [_config.yml](_config.yml) to `/YOUR-NEW-PRESENTATION` according to the name of your presentation path (click the file name in the list, the `edit` button then is on the right next to the red `delete` button, or go to [pages](pages)). You should also edit the title of the presentation, other settings can be left as is. Do not edit anything below `# Build settings`! Hit `Commit changes` to save your edit. With this commit you have just triggered the first build process of your new presentation.
5. Wait a minute for the build process to pass and head over to your new website at `https://YOUR-USER-OR-GROUPNAME.gp.hrz.tu-chemnitz.de/YOUR-NEW-PRESENTATION` (e.g. for this presentation, see result [https://ioer.gp.hrz.tu-chemnitz.de/common/presentation/](https://ioer.gp.hrz.tu-chemnitz.de/common/presentation/)). Sometimes, force-refresh (<kbd>F5+CTRL</kbd>) is necessary to update browser cache for the latest changes.
6. If you want to get your presentation available under https://YOUR-USER-NAME.ioer.info/YOUR-NEW-PRESENTATION, get in touch with Alexander Dunkel and Mario Bieh.

You may delete this file from the repository (red `delete` button), if you want to. It is not being rendered into the website, until you add a frontmatter to it.


Creating slides
---------------

There are some example slides within the `_posts` directory. Edit or delete them and create more slides by adding files with the `+` button. Name them after the scheme `XXXX-XX-XX-somename.md` where `X` is a numeral. The slides are sorted after their file names.

Add content to the page using Markdown syntax. [Read the help page for Markdown Syntax](https://gitlab.hrz.tu-chemnitz.de/help/user/markdown.md) (it's very easy!)

| Features          | Syntax                                                   |
|-------------------|----------------------------------------------------------|
| Fragments         | add `{% fragment %}` at the end of the line              |
| Vertical slides   | add `--` or `---` between slide content                  |
| Background color  | add e.g `{% background green %}` to the top of the slide |
| Speaker Notes     | add `Note:` to slide, everything below is a speaker note |
| Code snippets     | indent code by four spaces                               |

Also see the example slides in `_posts` directory.
