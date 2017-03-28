---
layout: post
title: Setup  GitHub Page
---

This post will show you how to write a markdown post for Jekyll on GitHub Pages. You will need:

* A computer
* A web browser
* An internet connection
* A GitHub account
* GitHub Desktop
* Atom text editor

## Clone to GitHub Desktop

You _could_ use the Editor on GitHub.com, but that's a bit limited, lets do some changes locally. Click the `Clone or download` button and click Open in Desktop.

![Clone to GitHubDesktop]({{ site.github.url }}/assets/write-jekyll-post/1_clone_to_desktop.PNG)

## Open in GitHub Desktop

Load up GitHub Desktop and find your repo.

![Open in GitHub Desktop]({{ site.github.url }}/assets/write-jekyll-post/2_open_in_desktop.PNG)

## Open in Atom

Use the quick access `Atom` button in GitHub Desktop to open the repo in Atom text editor.

![Open in Atom]({{ site.github.url }}/assets/write-jekyll-post/3_open_in_atom.PNG)

## Make a new folder

Use the right click to open the `New Folder` dialogue in Atom.

![Make a new folder]({{ site.github.url }}/assets/write-jekyll-post/4_new_folder.PNG)

## Name `_posts`

Name the new folder `_posts`. __This is really important. If you don't you're going to have a bad time.__

![Name posts]({{ site.github.url }}/assets/write-jekyll-post/5_name_folder.PNG)

Behind the scenes Jekyll is looking for this folder when the repo is hosted on the website. It will use the Markdown files in this folder to build the individual blog posts.

## New file

Use the right click again to open the `New Folder` dialogue in Atom.

![New file]({{ site.github.url }}/assets/write-jekyll-post/6_new_file.PNG)

## Name `2017-03-26-setup-github-pages` (or something similar)

Name the new folder `2017-03-26-setup-github-pages` or something similar. __This is also really important. If you don't you're going to have a bad time.__

![Name file]({{ site.github.url }}/assets/write-jekyll-post/7_name_file.PNG)

Behind the scenes Jekyll is looking for names with this structure when the repo is hosted on the website. It will use the structure of the file names to associate the date it was published with the file. The generic structure to use is `YYYY-MM-DD-my-post-title`.

## Include YAML frontmatter

Duplicate the following identically (or at least similarly) at the start of your file. __This is also also really important. If you don't you're going to have a bad time.__

![Include YAML frontmatter]({{ site.github.url }}/assets/write-jekyll-post/8_include_YAML_frontmatter.PNG)

Behind the scenes Jekyll is looking for this at the start of the files when the repo is hosted on the website. It will use this to associate metadata to the file. This is a minimal example, but they can be much more developed.

## Write some Markdown and Liquid objects

Markdown is a really convenient way to encode formatting into text files. It doesn't break the flow of the text file when it is being read raw, and is much easier to learn and type without errors than html. Liquid is a templating language which is used to provide logic and variables to a page which is rendered through Jekyll. You don't _need_ to use the nested structure here to locate files, I just find it helps.

![Write some Markdown and Liquid objects]({{ site.github.url }}/assets/write-jekyll-post/9_write_some_markdown_and_liquid_objects.PNG)

### Markdown
In this example the `##` denotes a second level header in Markdown. You can learn more about Markdown from your README that GitHub filled out for you in the last post. Markdown is also used to include a picture in the document via `![New repo](path/to/file.pic)`, however we've also used a Liquid object in `{{}}`...

### Liquid
When the site is built Jekyll will replace this argument `site.github.url` with the actual url of your site hosted by GitHub. Remember the last part of the last post? That url that GitHub assigned you which is recorded in your repo settings. You should get used to using Liquid, and you should always use {{ site.github.url }} when making pages to host on GitHub Pages. __This is also also also really important. If you don't you're going to have a bad time.__

## Commit your changes

Save your file and head back to GitHub Desktop. Commit your changes and then `sync` your changes back to the web hosted version.

![Commit your changes]({{ site.github.url }}/assets/write-jekyll-post/10_commit_changes.PNG)

In my example I've already made a few changes. I've also made a new branch called gh-pages to test out my changes before commiting to the main branch. You can change branch the site is built from in the settings page of the repo, however the branch has to be called either `master` or `gh-pages`.

## Find your page

After syncing changes, GitHub Pages will notice that you have a folder called `_posts`. It will look through the folder for `.md` files with a name following the structure `YYYY-MM-DD-my-post-title`, and will check the `YAML` at the front. If it finds all these in place it will then parse the Markdown and Liquid into HTML, and publish these to the internet. Where can you find it?

Well, right now I can find mine at https://davergp.github.io/JekyllHubDemo/2017/03/26/setup-github-pages.html. The structure is "https://githubusername.io/RepoName/YYYY/MM/DD/my/post/title". Don't get too excited though...

![Commit your changes]({{ site.github.url }}/assets/write-jekyll-post/11_find_page.PNG)

A bit disappointing. None of our neat github theme materials have been applied. All the material is there though we've got a couple more jobs to do. 
