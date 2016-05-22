---
title: How to use Hexo in Github Pages(1)
date: 2016-05-22 19:36:26
tags: Hexo, Github
---

Setup blog generator
===

### 1. Create repositories in Github.

- Create _<yourusername>.github.io_ repository for the Github Pages.
- Create another repository as the blog generator, I recommend using _<yourusername>.github.io.hexo_ in this case.

### 2. Install Hexo locally

Make should you have NPM and Git installed in your Linux/Mac machine.

``` bash
$ sudo npm install -g hexo-cli
```

### 3. Create a Hexo project

Create a new folder to hold the Hexo code. The folder name does not matter, I use __blog-generator__ in this case.

``` bash
$ hexo init blog-generator
$ cd blog-generator
```

### 4. Install deployer for git

Hexo could "compile" the blog source code to a static website. If you do:

``` bash
$ hexo generate
```

A _public_ folder is added which contains all the html and css files. However it still needs to know where to deploy the website.

``` bash
$ npm i -S hexo-deployer-git
```

### 5. Update Hexo config

Hexo has different deployment methods, you need to update the configuration to let Hexo can automatically deploy the blog website to Git.

Use any editor or __vi__ to update the __config.yml__, you could change a bunch of settings within this file. The most important configuration is the ___deploy___.

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

### 6. Deploy blog to Github Pages!

Now the Hexo could generate the static blog files, and push them to your _<yourusername>.github.io_ repository.
Open a browser with the URL _<yourusername>.github.io_ to see your Github Pages.

``` bash
$ hexo clean
$ hexo generate --deploy
```

### 7. Add blog generator to Git

Do not forget to add your Hexo code to Git.

``` bash
$ git init
$ git add ./
$ git commit -m 'some comments'
$ git remote add origin https://github.com/<yourusername>/<yourusername>.github.io.hexo.git
$ git push origin master
```