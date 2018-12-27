---
layout: post
title: Get some help for using git
subtitle: A collection of resources for getting started for git and for solving problems with git.
tags: [git, GitHub]
image: /img/git-logo-256.png
gh-repo: hardyscheel/hardyscheel.github.io
gh-badge: [follow]
---

<!--
A collection of resources for getting started for git and for solving problems with git.
-->

### Table of content
- [Tutorials](#tutorials)
- [Cheat Sheets](#cheat-sheets)
- [Solving Problems](#solving-problems)
- [FAQ](#faq)
    - [Change the user for a repository](#change-the-user-for-a-repository)

----

## Tutorials
Get to know git as a version control system.
- [Pro Git ebook in various languages](http://git-scm.com/book){:target="_blank"}
- [official git introduction tutorial](https://git-scm.com/docs/gittutorial){:target="_blank"}
- [a guided tour through git fundamentals](http://gitimmersion.com){:target="_blank"}
- [git for GitHub handbook](https://guides.github.com/introduction/git-handbook/){:target="_blank"}

---

## Cheat Sheets 
Get a quick overview of relevant git commands for your daily work.
- [git cli cheat sheets - overview - @github.com](https://services.github.com/on-demand/resources/cheatsheets/){:target="_blank"}
- [git cli cheat sheets - german - @github.com](https://services.github.com/on-demand/downloads/de/github-git-cheat-sheet/){:target="_blank"}
- [git cli cheat sheets - english - @github.com](https://services.github.com/on-demand/downloads/github-git-cheat-sheet/){:target="_blank"}
- [git cli cheat sheets - english PDF - @github.com](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf){:target="_blank"}

---

## Solving Problems
- [Setting up multiple GitHub accounts on Windows](http://www.kevinpelgrims.com/blog/2012/07/20/setting-up-multiple-github-accounts-on-windows/){:target="_blank"}

---

## FAQ

### Change the user for a repository
Git uses a hierarchical configuration of multiple levels. Settings in higher levels override values in lower levels. Lower levels inherit from higher levels (eg. local inherits from global).
- **system** - Settings for all users of the system are stored in git installation folder: your-git-installation-folder/etc/gitconfig
- **global** - Settings for the current user are stored locally in your user home directory: ~/.gitconfig
- **local** - The current repository settings are stored locally in the repository directory: .git/config

You can configure an individual repository to use a specific user which overrides the global configuration. From the root directory of the repository, run the following on command line:
~~~
$ git config user.name "your name"
$ git config user.email your@email.com
~~~

The default user for all repositories is configured in the global configuration file in your home directory ~/.gitconfig. You can also run the following from command line:
~~~
$ git config --global user.name "your name"
$ git config --global user.email your@email.com
~~~
