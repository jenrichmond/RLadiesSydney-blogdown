---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: "MarkyMark 1"
menu:
  ryouwithme:
    parent: MarkyMark
    weight: 2
title: MarkyMark 1
toc: true
type: docs
weight: 5
---

#  Formatting in R Markdown

Now that you have loaded your data into R, cleaned it up, and made some impressive looking plots, you probably want to show your analysis to someone else, who may or may not be an R user. R Markdown is a really easy way of creating analysis reports to share with others. It is also a useful tool for making sure that the analysis you do is well-documented and reproducible; use R Markdown and your future self will thank you. 

In this lesson, we are going to walk through how to create a report using R Markdown, how to format text within your report, and add links, images, and gifs. 

## Lesson Outcomes
By the end of the lesson, you should be able to:

* 1.1 Create a R Markdown document (rmd file)
* 1.2 Use heading levels to create your document structure
* 1.3 Make text bold and italics, and use quotes
* 1.4 Add links, images, tweets, and gifs to your report 

## How to create a R Markdown document and format text within it

In this screencast, we’ll cover:

  * How to create a R Markdown document and `knit` it into a report 
  * How to use headings, bold, italics, and quotes within your report 


<iframe width="560" height="315" src="https://www.youtube.com/embed/YATLwVrvjVw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:

1. Open a new R Markdown document and save it
2. Knit the document
3. Delete everything in the default template and knit it again 
4. Play around with headings, putting text in bold and italics, and adding quotes

## How to insert links, images, tweets and gifs 

### Links 
You can embed links to other web content in your R Markdown document using a combination of square and round brackets. 

Put the words that you want to use as the link in square brackets, and the url that you want to link to in round brackets. 

> `[find Rmd resources here](https://github.com/jenrichmond/RMarkdownThrowdown)`



### Images

Use similar notation to insert an image...

> `![](nameofimage.png)`


### Gifs and Tweets 

To embed gifs and tweets, choose "embed" ... 

![](/workshop/04-MarkyMark-1_files/tweet1.png)

... and just copy and paste the code into your R Markdown document. 

![](/workshop/04-MarkyMark-1_files/tweet2.png)


In this screencast, we’ll cover:

  * How to create links, add images, and embed tweets/gifs in a R Markdown document 
  
<iframe width="560" height="315" src="https://www.youtube.com/embed/9mmNO2M1zSg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:

1. Write a sentence about your favourite Tidyverse package in your .rmd document and insert a link to the vignette page for that package
2. Insert an image of the hex for that package into your document
3. Find a tweet about your favourite package and insert that into your document 
4. Find the famous gif of Hadley Wickham typing code and embed that into your document 
5. Knit your document!

## Learn More
To learn more about formatting your R Markdown document, check out the [R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/), a free book written in bookdown, by Yihui Xie.  

As per usual, Sydney-based R-Ladies are encouraged to share (and vent) on Slack at #ryouwithme_4_markymark!

Next up in MarkyMark, lets talk about chunks. Head on to Lesson 2!
