---
title: Hexo Test Drive
date: 2017-04-26 21:46:19
tags: 
  - Hexo
  - NexT
  - Github Pages
---

## Introduction 
Hexo is an alternative of jekyll to create static blog pages from markdown on Github Pages. Implemented with nodejs, Hexo is quite easy to use compared with jekyll. Using Hexo and a theme named "NexT", I am here now to demonstrate how to create a pretty nice blog site on Github Pages within just a few minutes.

<!-- more --> 

## Prerequisites
To begin with, you'll need:
* node 
* git 
* a github account


## Step By Step
### 1. install hexo
``` bash
npm install -g hexo-cli

```
### 2. create git repository
Create a git repository with the name bellow:
```
<username>.github.io
```
Just leave it empty and don't initialize it with .gitignore or README.md or LICENSE.

### 3. initialize your blog directory
Initialize your git repository directory structure locally
``` bash
mkdir <username>.github.io
cd <username>.github.io

# init hexo source 
hexo init .

# test you hexo, check http://localhost:4000 in your browser.
hexo serve 

# init git repository
git init
git add .
git commit -m "first commit"
git remote add origin git@github.com:<username>/<username>.github.io

# IMPORTANT, do NOT push to your master branch 
# See Github Pages help page for more details.
git branch -m master source
git push -u origin source
```

### 4. config your blog site
Open _config.yml and modify options as your wish. Here's some of them that may be useful.
* title
* author
* url 
* language
* theme: change to "next" if you wanna replace the default one
* deploy: the git branch should be master
``` yaml
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:<username>/<username>.github.io.git
  branch: master
```
Check out a more-detailed document on [Hexo official pages](https://hexo.io/docs/configuration.html)

### 5. ( optional ) switch blog theme to "NexT"
1. First remove default theme: landscape
``` bash
rm -rf themes/landscape
```
2. Download Hexo "NexT" theme release package, and do not use git submodule since we have to modify its config files later.
```
wget https://github.com/iissnan/hexo-theme-next/archive/v5.1.1.zip
```
3. unzip theme content to theme/next folder
4. config theme as your wish in theme/next/_config.yml
5. check out config docs for more details.[](http://theme-next.iissnan.com/theme-settings.html)

### 6. deploy to Github Pages
``` bash
hexo clean && hexo generate && hexo deploy
```
### 7. submit your source code 
Remember to submit your code to git repository in a different branch.
```
git push
```
### 8. check out your Github Pages blog site.


## Keep posting blogs using Hexo
### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/deployment.html)



## References
* [Hexo](https://hexo.io/)
* [NexT](http://theme-next.iissnan.com/)
* http://feisky.xyz/
