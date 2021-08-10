---
layout: post
author: rgalindor
title: Enviroments encapsulated
subtitle: Some things work better isolated
excerpt: Encapsulate your environment
background: '/img/posts/01.jpg'
comments: true
usemathjax: true
---

A few years ago I heard that the smartest people are also the laziest people. That is because a lazy person looks for a better way not to waste efforts working on dumb (repetitive) tasks, and they often succeed in that! I think that deploying is currently one of the most annoying processes related to data science and bioinformatics. So, now you need to deploy better your code to be considered a good developer.  

As a bioinformatician, you must be aware of the annoying times when you have to install very specific software in very different environments on very different computers. It scales quickly and you know there is so much code susceptible to carry a dependency mistake. Fortunately, this is not only a matter of bioinformaticians but for all types of developers.

So, people faced the same annoying dependencies errors all over the developer community. And some ideas like _containers_, started to brighten due to advances in engineering. Containers can encapsulate related things that do not require anything from outside to operate. Then some projects like [docker](https://www.docker.com) and [kubernetes](https://kubernetes.io) started to become priorities. 

Some `python` communities were also creating different ways to create _containers_. Eventually `conda` [project](https://docs.conda.io/) emerges as a _package manager_ that is also a _environment manager_. So now you can install, run and update software within an environment which is a _container like_ space, and it does not conflict with any software outside itself. That is tremendously useful, the days when you need to use `alternatives` are gone. 

Using conda is as simple as:

```
conda create --name my_env
conda activate my_env
```

And that is it! Now you have an environment isolated from the outside, you can break stuff there and there is no problem to the outside because you just need to type

```
conda deactivate
```

to return to the global configuration.

Obviously, you want to perform some `install`, `update`, etc. inside `my_env`. That is where the magic happens, but it is a topic for another post.

