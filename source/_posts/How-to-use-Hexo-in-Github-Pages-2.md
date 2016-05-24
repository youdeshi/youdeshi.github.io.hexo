---
title: How to use Hexo in Github Pages(2)
date: 2016-05-23 19:20:58
tags:
- Hexo
- Github
---
___
Start to write your blog
===

### 1. Create a new post

You could create a draft first then publish the draft later.

``` bash
$ hexo new draft testPost1
$ hexo publish testPost1
```

Or you could create a post directly.

``` bash
$ hexo new testPost2
```

Or you could create a page.

``` bash
$ hexo new page testPage1
```

### 2. Edit/Delete a post

No command is needed, you could go to the __source__ folder, then edit/delete the corresponding files.

#### 2.1. Use Block Quote

Perfect for adding quotes to your post, with optional author, source and title information.

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}
```

#### 2.2. Use Code Block

Useful feature for adding code snippets to your post.

```
{% codeblock [title] [lang:language] [url] [link text] %}
code snippet
{% endcodeblock %}
```

Backtick Code Block is identical to using a code block, but instead uses three backticks to delimit the block.

```
``` [language] [title] [url] [link text] code snippet
```


#### 2.3. More Tag Plugins

Inserts an image with specified size

```
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
```

Inserts a link with *target="_blank"* attribute.

```
{% link text url [external] [title] %}
```

[See More](https://hexo.io/docs/tag-plugins.html)

### 3. Run server to test

To start using the server, you will first have to install _hexo-server_.

``` bash
$ npm install --save hexo-server
$ hexo server
```

Your website will run at http://localhost:4000 by default. Use the _-p_ option to set a different port.

```bash
$ hexo server -p 8081
```

### 4. Generate static files and deploy

```bash
$ hexo generate --deploy
```