---
layout: post
title: get some help for using git
tags: [git, GitHub]
image: /img/git-logo.png
---

A collection of ressources for getting started for git and for solving problems with git.

## Tutorials
Get to know git as a version control system.
- [Pro Git ebook in various languages](http://git-scm.com/book)
- [official git introduction tutorial](https://git-scm.com/docs/gittutorial)
- [a guided tour through git fundamentals](http://gitimmersion.com)
- [git for GitHub handbook](https://guides.github.com/introduction/git-handbook/)

## Cheat Sheets 
Get a quick overview of relevant git commands for your daily work.
- [git cli cheat sheets - overview - @github.com](https://services.github.com/on-demand/resources/cheatsheets/)
- [git cli cheat sheets - german - @github.com](https://services.github.com/on-demand/downloads/de/github-git-cheat-sheet/)
- [git cli cheat sheets - english - @github.com](https://services.github.com/on-demand/downloads/github-git-cheat-sheet/)
- [git cli cheat sheets - english PDF - @github.com](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf)

## Solving Problems
- [Setting up multiple GitHub accounts on Windows](http://www.kevinpelgrims.com/blog/2012/07/20/setting-up-multiple-github-accounts-on-windows/)

## FAQ

### change the user for a repository
Git uses a hierarchical configuration of multiple levels. Settings in higher levels override values in lower levels. Lower levels inherit from higher levels (eg. local inherits from global).
- system - Settings for all users of the system are stored in git installation folder: your git installation folder/etc/gitconfig
- global - Settings for the current user are stored locally in your user home directory: ~/.gitconfig
- local - The current repository settings are stored locally in the repository directory: .git/config

You can configure an individual repository to use a specific user which overrides the global configuration. From the root directory of the repository, run the following on command line:
~~~
$ git config user.name "YOUR NAME"
$ git config user.email your@email.com
~~~

The default user for all repositories is configured in the global configuration file in your home directory ~/.gitconfig. You can also run the following from command line:
~~~
$ git config --global user.name "YOUR NAME"
$ git config --global user.email your@email.com
~~~
