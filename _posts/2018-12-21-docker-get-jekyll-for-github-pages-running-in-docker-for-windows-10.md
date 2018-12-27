---
layout: post
title: Get Jekyll for GitHub Pages running in Docker for Windows 10
subtitle: Run a Docker container with Jekyll. Build GitHub Pages on your local machine.
tags: [Docker, Jekyll]
image: /img/docker-logo-512.png
gh-repo: hardyscheel/hardyscheel.github.io
gh-badge: [follow]
---

In this article I address some most common problems when working with Docker on Windows 10. Today we want to get up running Jekyll in Docker. The most common problems you encounter occur in file system path translations when using docker commands. And the second problem you may not think about is the choice of command line. Do you use cmd.exe, PowerShell or a linux command line like MSYS or Cygwin? You must take care of the path variables when using a command line.

### Table of content

- [Prerequisite: activate 'Shared Drive' in Docker settings](#prerequisite-activate-shared-drive-in-docker-settings)
- [Run a Jekyll container](#run-a-jekyll-container)
- [Resources for further reading](#resources-for-further-reading)

----

## Prerequisite activate 'Shared Drive' in Docker settings

Activate 'shared drive' to let docker containers access your hard drive. A tcp port 445 in your Windows Host firewall will be opened for communication between your Windows host (10.0.75.1) and the docker vm (10.0.75.2).

From time to time it is neccessary to renew the credentials for a shared drive in docker. Espeacially when you get docker error like your host path is not accessable or other bind mount errors. To do so, simply deactivate and activate the shared drive setting.

To test if you can get access to your mounted drive, you can start an alpine linux bash and navigate to your mounted smb drive C:\ like this:

To start alpine linux and bind Windows drive C:\ to alpine linux /path/ path, type in cmd.exe:
~~~
$ docker run --rm -it -v C::/data alpine sh
~~~

A bash on alpine linux starts. You can now list the content of the mounted /data/ path in your alpine linux container. It should contain your drive C:\ on your Windows host.
~~~
$ ls /data/
~~~

## Run a Jekyll container

Navigate to your Jekyll project. Open cmd.exe. From here we use %C% to tell 
Docker that we want to bind the current project directory to the Jekyll container path: /user/src/app.
~~~
$ docker run -v %CD%:/usr/src/app -p "4000:4000" starefossen/github-pages
~~~

## Resources for further reading

- [Running Jekyll in Windows Using Docker](https://www.jamessturtevant.com/posts/Running-Jekyll-in-Windows-using-Docker/){:target="_blank"}
- [Installation Docker for Windows on Windows 10](https://gerardnico.com/vm/docker/installation_windows_10){:target="_blank"}
- [Docker documentation: shared drives](https://docs.docker.com/docker-for-windows/#shared-drives){:target="_blank"}
- [Use Docker as your local environment for your GitHub Pages site](https://code.ricalo.com/docker/github-pages/GitHub-Pages-Docker/){:target="_blank"}
- [Running Jekyll in Windows Using Docker](https://www.jamessturtevant.com/posts/Running-Jekyll-in-Windows-using-Docker/){:target="_blank"}
- [Creating and Hosting a Personal Site on GitHub](https://jmcglone.com/guides/github-pages/){:target="_blank"}
