---
layout: post
author: rgalindor
title: Interactive plotting path
subtitle: Because static plots are in the past
excerpt: A history of how to plot interactive
background: '/img/posts/04.jpg'
comments: true
usemathjax: true
---

I was remembering 15 years ago. By that time, I used to plot data with _Excell_, I did not have any alternative. However, I started to get used to `R`. I finally have the tool to extract information from bare data.

I first used `R` because I needed to process biological data. I was comfortable writing code in `perl`, mainly because much of the data I was using were _biological sequences_, so it was sufficient. However, I realized data simulation could be a headache in `perl`, then `R` appears to be a good alternative. Furthermore, plotting results for my dissertation was pretty straightforward so I become more fluent in `R`.

For several years I used only `plot()` function (and also `hist()` and `image()`), because I told myself that using code from libraries was a signal of weakness. You know, juvenile thoughts about non-significant things. I refused to learn new syntaxis, and until 2017 I never used `ggplot2` library. 

I remember when I was trying to figure out how to build a [sunburst visualization](https://datavizcatalogue.com/methods/sunburst_diagram.html), and because one of my best friends I take a look on [D3](https://d3js.org/). One thing drove me to another until I arrive at `plotly`. Then I started to go deep and I found that `plotly` was also in `python` as well as in `julia`. So I started to use it. It was a big surprise to me that there was a `ggplotly()` function that allows regular users of `ggplot2` to provide interactivity to their plots, so I was forced to learn `ggplot2` (and all the `tidyverse` package).

Well finally I started to use interactive plots such as the following

```R
ggplot(aes(x=performance, y=ofensive, size=defense, color=matches, text=team)) +
geom_point() +
labs(title="Performance vs offensiveness of National Teams in matches of FIFA World Cup") -> p
ggplotly(p) 
```

<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://rgalindor.github.io/football-international/standalone/performance_vs_offensive_FIFAwc.html" height="525" width="100%"></iframe>

And yes, this was the history of how I learned `ggplot2` in just the opposite way you normally learn it.

