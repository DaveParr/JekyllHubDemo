---
layout: post
title: Apply theme to posts
---

## Jekyll layouts

Jekyll is looking at each post and taking the argument `layout` from it. It uses this to apply `.html` layouts to the file. The `.html` file itself is looking at your `.css` style sheets. What do you mean you didn't write any?

GitHub Pages wrote it for you and hid it in folders you don't see in your repo. Just take a look at DevTools or equivalent.

![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/1_devtools_index.PNG)

![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/2_devtools_css.PNG)

### The quick fix

If you've been paying attention you'll spot that you can simply go through all your posts and replace `layout: post` with `layout: default`. However, there's a more sophisticated option...

### The GitHub Pages Organization

There is an organization account that holds all the information for all the supported themes (remember step 1?) in one place. Got to https://github.com/pages-themes, and find your theme. [Cayman has some great guidance on modifying the theme.](https://github.com/pages-themes/cayman)

## Modify the css

### Create a css file

Create folders and a file at

```
/assets/css/style.scss
```

### Add some frontmatter (sort of)

Add the following at the top of the file

```
---
---

@import "{{ "{{ site.theme " }}}}
```

There is a `yaml` fence there, but it's empty. After that there is an import rule and a liquid tag.

### Modify the css

Say I wanted to make headers at level 1 purple, I would use normal `.css` after the import tag.

```
---
---

@import "{% raw  %}{{ site.theme }}{% endraw %}";

h1 {
  color: purple;
}
```

#### Before

![DevTools]({{ site.github.url }}/assets/setup-index-page/3_index_page.PNG)

#### After

![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/4_index_after.PNG)

## Modify the layout

What if you want to do something more complex, for example creating a different design for the posts compared to the rest of the site? Remember our friend `_posts`?

### Create a layouts file

Create folders and a file at

```
/_layouts/default.html
```

This will be a central place for Jekyll to check our different layouts. __This is really important. If you don't have it you're going to have a bad time.__

### Copy the original

Find your original layout for the theme.

![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/5_original_layout.PNG)

### Paste the copy

Paste your copy into the file you just created

### Find the `{% raw %}{{ content }}{% endraw %}` liquid object

It's important to find this part in the `.html`

```
<section class="main-content">
  {% raw %}{{ content }}{% endraw %}
```

This section is the part that sources your parsed Markdown material and then places it in the `.html`. __This is really important. If you don't have it you're also going to have a bad time.__

### Duplicate the copy

Take a copy and rename as `posts.html`

### Modify the copy

I want to change my header on my posts page to display the post title and date instead of the project title and description

#### Before

```
<body>
    <section class="page-header">
      <h1 class="project-name">{% raw  %}{{ site.title | default: site.github.repository_name }}{% endraw %}</h1>
      <h2 class="project-tagline">{% raw  %}{{ site.description | default: site.github.project_tagline }}{% endraw %}</h2>
      {% raw  %}{% if site.github.is_project_page %}{% endraw %}
        <a href="{% raw  %}{{ site.github.repository_url }}{% endraw %}" class="btn">View on GitHub</a>
      {% raw  %}{% endif %}{% endraw %}
```
![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/6_post_head_before.PNG)

#### After

```
<body>
  <section class="page-header">
    <h1 class="project-name">{% raw  %}{{ page.title }}{% endraw %}</h1>
    <h2 class="project-tagline">{% raw  %}{{ page.date | date_to_string }}{% endraw %}</h2>
```
![DevTools]({{ site.github.url }}/assets/apply-theme-to-posts/7_post_head_after.PNG)
