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

### 3. Use Block Quote

Perfect for adding quotes to your post, with optional author, source and title information.

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}
```

As an example, add following to __testPost1__

```
{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}
```

### 4. Use Code Block

Useful feature for adding code snippets to your post.

```
{% codeblock [title] [lang:language] [url] [link text] %}
code snippet
{% endcodeblock %}
```

As an example, add following to __testPost1__

```
{% codeblock _.compact lang:javascript http://underscorejs.org/#compact Underscore.js %}
_.compact([0, 1, false, 2, '', 3]);
=> [1, 2, 3]
{% endcodeblock %}
```

Backtick Code Block is identical to using a code block, but instead uses three backticks to delimit the block.

```
``` [language] [title] [url] [link text] code snippet ```
```

### 5. More Tag Plugins










