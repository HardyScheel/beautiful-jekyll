This is the source code of the theme for my personal blog at [hardyscheel.de](https://hardyscheel.de){:target="_blank"} hosted at GitHub Pages. Based on a the Jekyll template & theme [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll){:target="_blank"} by Dean Attali.
If you want to try or run your own Jekyll blog on GitHub Pages, you can get good help and introduction at [Beautiful Jekyll](https://deanattali.com/beautiful-jekyll){:target="_blank"} from Dean.

I extended and customized this Jekyll template to my own needs. My basic idea was to build a reusable component based blog. I'm fairly new to Jekyll and there is a long way to go before I can publish my own Jekyll templates and themes.

To run this blog at [hardyscheel.de](https://hardyscheel.de){:target="_blank"} the following things are involved:
- [*GitHub Pages*](https://pages.github.com/){:target="_blank"} as a webhoster
- [*Jekyll*](https://jekyllrb.com/){:target="_blank"} - A static website generator especially useful for blogs written in Ruby. Served by GitHub Pages.
- [YAML](https://yaml.org/){:target="_blank"} - YAML data serialization language is build in the template to make fast configurations all across the web site.
- [*Bootstrap*](http://getbootstrap.com/){:target="_blank"} & [*jQuery*](https://jquery.com/){:target="_blank"} - For building some layout and gui components.

### Table of contents
- [Jekylls role as a static site generator](#jekylls-role-as-a-static-site-generator)
- [Template layout](#template-layout)
    - [Available YAML Front Matter variables](#available-yaml-front-matter-variables)
- [Prose.io as web based content authoring editor](###prose-as-web-based-content-authoring-editor)

---

## Jekylls role as a static site generator
Static site generator means that the pages are built just once and just being served when their URL is hit, rather than being dynamically created with every page load.

## Template layout
This is a reusable template to use it for other projects, so components are generalised and reusable as possible. A good starting point to learn to how to build components.

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
In combination with [Prose.io](https://prose.io/#about){:target="_blank"}, a webbased content authoring environment, you can use Prose as a MarkDown editor to add and edit blog posts very quickly. To use it on your own you have to give Prose.io access to your GitHub account if the source code of your Jekyll blog is hosted at GitHub Pages.
