This is the source code of the theme for my personal blog at [hardyscheel.de](https://hardyscheel.de) hosted at GitHub Pages. Based on a the theme [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll) by Dean Attali. My basic idea was to build a reusable component based blog. The same idea Dean had. So I can start learning following this concept by examining his work.
Feel free to use my theme or get even more help and introduction to run your own blog on GitHub Pages at [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll) from Dean.

I extended and customized the [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll) template to my own needs. In the meanwhile I learn to build my own templates with the concept of reusable components in mind.

To run this blog at hardyscheel.de the following software components and techniques are involved:
- [*Jekyll*](https://jekyllrb.com/) - A static website generator especially useful for blogs written in Ruby. Served by GitHub Pages.
- [*Bootstrap*](http://getbootstrap.com/) & [*jQuery*](https://jquery.com/) - For building some layout and gui components.
- [YAML](https://yaml.org/) - YAML data serialization language is build in the template to make fast configurations all across the web site.

### Table of contents
- [Jekylls role as a static site generator](#jekylls-role-as-a-static-site-generator)
- [Template layout](#template-layout)
    - [Available YAML Front Matter variables](#available-yaml-front-matter-variables)
- [Prose.io as web based content authoring editor](###prose-as-web-based-content-authoring-editor)

---

## Jekylls role as a static site generator
Static site generator means that the pages are built just once and just being served when their URL is hit, rather than being dynamically created with every page load.

## Template layout
The basic idea of this theme was to make a reusable template to use it for other projects, so components are generalised and reusable as possible. A good starting point to learn to build components.

### Available YAML Front Matter variables

```YAML
---
layout: page | post | minimal
title:	Your big heading on the specific page or post.
subtitle: Your site or blog description that wents under the title.
image: The path to your image like '/path/to/img'.
show-avatar:  (false) | true - Tiny picture the top center of the site.
bigimg:	Big image as a background for the big title and subtitle. Use '/path/to/img'.
tags: [java, html] Add tags of your choice.

-- Jekyll optional vars
date: overrides the date from the file name YYYY-MM-DD HH:MM:SS
permalink: (default /year/month/day/title.html)
published: (true) | false

-- Theme based optional vars
comments: (false) | true
show-avatar: (true) | false
social-share: (false) | true - Social media buttons on the bottom of the site.
use-site-title: (false) | true - The title of the web site is shown instead of the specific page or post title.
---
```

## Prose as web based content authoring editor
In combination with [Prose.io](https://prose.io/#about), a webbased content authoring environment, you can use Prose as a Markdown editor to add and edit blog posts very quickly. To use it you have to give Prose.io access to your GitHub account where the source code of your Jekyll templated blog is hosted.

