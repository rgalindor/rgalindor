---
layout: post
author: rgalindor
title: Some styles in markdown
subtitle: Cool stuff that you can do easily
excerpt: Making big impact with minimum effort
background: '/img/posts/03.jpg'
comments: true
usemathjax: true
---

# Some styles in mardown

Create web content was a serious challenge 10 years ago. Now you only need some knowledge of [github](https://github.com), a few hours of Jekyll configuration, and that is it! Of course, you also need to use markdown, but it is pretty easy.

## Markdown

This language is what engineers use to document their code. When coding you do not have time to create a very pretty documentation, you can not waste time _beautiflying_ a manual, but you also can not distribute your manuals in plane text (not now). So markdown has been developed to do that type of work, simplifying how to write a cool manual with just a few text enrichment rules.

In markdown you can create simple text, _italic text_, **bold text** and even ***italic-bold text***, you just need to remember.

 - Use `_italic text_` to create _italic_
 - Use `**bold text**` to create **bold**
    - You can combine _italic_ and **bold** ``**_italic-bold text_**` to create ***italic-bold*** 

Also you just see how to create a list using `-` in the code. 

Speaking of code, I just used `\`` to create words intended to mean code words, but you can even create whole blocks of code in this way:

```bash
pwd
ls -lh /path/to/folder
dmesg
```

So reviewing stuff that we can create very easy:

 1. You can use **different** _types_ of font **_styles_**
 2. You can write `code`
 3. You could list things with `-` at the beginning (or with `1.` to  have an ordered list).

### Cool things to implement very easy 

So, having text is very important, however there are other types of structures that can comunicate more effective messages that are usually complex. For example, you can make a [link](https://github.com/rgalindor) very easy: `[words displayed](url)`. And if such pointed resource is an image:

![alt text](https://rgalindor.github.io/img/posts/01.jpg)

Another common structure that can be implemented very easy are tables:

```
| Header | Column |
|--|--|
| item 1 | item 2 |
| item 3 | item 4 |
```

results in

| Header | Column |
|--|--|
| item 1 | item 2 |
| item 3 | item 4 |

### Extras

So, with all the structures you can implement on `markdown` you can create any type of content. However if you connect your code (using `kramdown` from `jekyll`) to platforms such as [github-pages](https://pages.github.com). You can even use $$LaTeX$$ code to create some equations:

\\[E=mc^{2}\\]

Maybe you are a fan of emojis. Good news, there is a plugin `jemoji` that you can use to :smiley:

And finally you could combine all these structures to have a very interesting way to communicate all the things that plane text can not.


| Mathjax | Emojis | Code |
|--|--|--|
| $$E=mc^{2}$$ | :sunglasses: | `R` |
| $$\frac{\lambda_{i}}{\alpha^{\sqrt{n}}}$$ | :alien: | `perl` |


Setting up things here could be easier.

