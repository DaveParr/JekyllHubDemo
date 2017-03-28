---
layout: post
title: Setup index page
---

This post will show you how to write a an index of blog posts for Jekyll on GitHub Pages.

## Make a new folder named blog and a new file named index.html

I won't show you how to do this.

## Setup your frontmatter

Write your YAML exactly like below. Well, you can use a different title if you want.

![Setup your frontmatter]({{ site.github.url }}/assets/setup-index-page/1_setup_frontmatter.PNG)

Notice we're doing something different here. We are using an `.html` file not a `.md` file. We're also using a different layout argument, `default`, not `post` as in the other pages.

## Include liquid indexing

Write exactly the code below:

![Liquid indexing]({{ site.github.url }}/assets/setup-index-page/2_liquid_indexing.PNG)

Remember we're in an `.html` file? We've written some tags here, for unordered list and list items. We've also got lots of liquid outputs in `{{ "{{ this " }}}}` and even liquid tags `{{ "{% this " }}%}`. The difference is important.

* Liquid objects `{{ "{{ this " }}}}` - resolve into text
* Liquid tags `{{ "{% this " }}%}` - apply logic to the template

So here we are using objects to reference parts of the site, pulling at various points page titles, posts on the site, dates and titles of posts. We actually iterate some logic for these objects with the tags to return a list with these details.

## Commit and sync your changes

You're on your own here too

## Check your page

Go back to your page URL (psst! remember it's in the repo settings).

![Index page]({{ site.github.url }}/assets/setup-index-page/3_index_page.PNG)

We've found the missing posts! Anything else surprise you? A few things have happened here.

> Jekyll has picked your new file as the home page.

This is because you called it `index.html`, Jekyll will default to display index if this is on the root folder.

> Jekyll has applied the old formatting for headers and footers

Look back at the `README.md`. That didn't _actually_ have any code to do any of the fancy formatting for the theme at all.

## Open a post

Now open up one of those lost posts.

![Open post]({{ site.github.url }}/assets/setup-index-page/4_open_post.PNG)

Hmmm, a bit of a let down. All that nice formatting on the home page isn't reaching your posts. Not done yet!
