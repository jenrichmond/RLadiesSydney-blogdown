---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: "MarkyMark 2"
menu:
  ryouwithme:
    parent: MarkyMark
    weight: 3
title: MarkyMark 2
toc: true
type: docs
weight: 5
---

#  Code Chunks in R Markdown

The real power of R Markdown comes when you start combining text and code. There are MANY advantages of putting notes alongside the code you are running. Even if your future self is the only person who benefits from those notes, they are invaluable. By using code chunks, R Markdown keeps the code with the output too, so someone else looking at your analysis can see what code you ran and what output you got. 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Me when I revisit my code from a few months ago: <br>I’m getting to be more thorough with my comments, I promise! 😫 <a href="https://twitter.com/hashtag/DataScience?src=hash&amp;ref_src=twsrc%5Etfw">#DataScience</a> <a href="https://twitter.com/hashtag/rstats?src=hash&amp;ref_src=twsrc%5Etfw">#rstats</a> <a href="https://twitter.com/hashtag/BiosystemsAnalyticsLab?src=hash&amp;ref_src=twsrc%5Etfw">#BiosystemsAnalyticsLab</a> <a href="https://t.co/NiXRTorbhd">pic.twitter.com/NiXRTorbhd</a></p>&mdash; Emine Fidan (@Em_The_Engineer) <a href="https://twitter.com/Em_The_Engineer/status/1101573335480180737?ref_src=twsrc%5Etfw">March 1, 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


In this lesson, we are going to walk through how to use code chunks in R Markdown to create a reproducible report.  

## Lesson Outcomes
By the end of the lesson, you should be able to:

* 2.1 Insert chunks of code in your R Markdown document
* 2.2 Use the chunk settings to control what appears in your report 

## How to insert code chunks

In this screencast, we’ll cover:

  * How to insert code chunks 
  * How to control what appears in your document when you knit 


<iframe width="560" height="315" src="https://www.youtube.com/embed/zuehNWUPRbM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:

1. Insert chunks to load the tidyverse package and read in the sydneybeaches data
2. Insert chunks to recreate your favourite plot from [VizW(h)iz](../03-vizwhiz-0/)
3. Knit your document, changing the chunk settings so that only the code and output appear in your document. 

Sydney-based R-Ladies, head on over to the #ryouwithme_4_markymark channel in Slack to share your code chunk successes (or woes!).

Next up, Lesson 3 tackles export formats!
