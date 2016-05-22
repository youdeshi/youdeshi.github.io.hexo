---
title: How to use Hexo in Github Pages(1)
date: 2016-05-22 19:36:26
tags: Hexo Github
---

Setup blog generator
===

### 1. Create repositories in Github.

- Create _<yourusername>.github.io_ repository for the Github Pages.
- Create another repository as the blog generator, I recommend using _<yourusername>.github.io.hexo_ in this case.

### 2. Install Hexo locally

``` bash
$ sudo npm install -g hexo-cli
```

Make should you have NPM and Git installed in your Linux/Mac machine.

### 3. Create a Hexo project

``` bash
$ hexo init blog-generator
$ cd blog-generator
```

Create a new fold to hold the Hexo code. The fold name does not matter, I use __blog-generator__ in this case.

### 4. Install deployer for git

``` bash
$ npm i -S hexo-deployer-git
```

### 5. Update Hexo config

``` bash
$ vi _config.yml
~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/<yourusername>/<yourusername>.github.io.git
  branch: master
```

Use any editor or __vi__ to update the __config.yml__, you could change a bunch of settings within this file. The most important configuration is the ___deploy___

### 6. Deploy blog to Github Pages!

``` bash
$ hexo clean
$ hexo generate --deploy
```

The hexo has generated the static blog files, and push all of them to your _<yourusername>.github.io_ repository.
Open a browser with the URL _<yourusername>.github.io_ to see your Github Pages.

### 7. Add blog generator to Git

``` bash
$ git init
$ git add ./
$ git commit -m 'some comments'
$ git remote add origin https://github.com/<yourusername>/<yourusername>.github.io.hexo.git
$ git push origin master
```