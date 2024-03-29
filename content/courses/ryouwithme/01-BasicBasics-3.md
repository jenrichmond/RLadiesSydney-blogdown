---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: "BasicBasics 3"
menu:
  ryouwithme:
    parent: BasicBasics
    weight: 4
title: BasicBasics 3
toc: true
type: docs
weight: 2
---

# Getting data into RStudio

In this, the third lesson to [Basic Basics](../01-BasicBasics-0/), we're going to review how to get data into RStudio, using a specially selected data file that we'll continue to use for many of the RYouWithMe lessons.

## Lesson Outcomes
By the end of the lesson, you should:

* 3.1 Have the `sydneybeaches.csv` data file saved to your RYouWithMe data folder
* 3.2 Know how to use the `here` package to tell R where your data is, how to use `read_csv` to read data from a .csv file, and how to use summary functions to explore your data
* 3.3 Have an idea of where to go to learn more about reading different kinds of data into R 

## 3.1 Get some data!

Okay, if we're going to discuss how to import data into R, then the first thing we'll need to do is have a data set! For this lesson we'll make it as painless as possible... click on [this link](https://raw.githubusercontent.com/rladiessydney/RYouWithMe/master/sydneybeaches.csv), which will take you to the raw sydneybeaches data on github, then right click and save the data as a .csv file. Put the .csv file in your `data` folder inside your `RYouWithMe` folder.

## Interlude... the Sydney beaches data

We'll be using this dataset for many of the remaining RYouWithMe lessons. Not only is it locally relevant for R-Ladies Sydney, it's also fascinating!  This dataset is compiled by the NSW Office of Environment and Heritage contains the enterococci counts in water samples obtained from -- you guessed it -- Sydney beaches as part of the [Beachwatch Water Quality Program](https://www.environment.nsw.gov.au/topics/water/beaches/beachwatch-water-quality-program)! The dataset we'll be working with is current as of October 13th 2018. 

What's enterococci, you ask? Whether you really want to know the answer depends on if you want to feel comfortable swimming in the Sydney region ever again...

From the Program (emphasis added):

>Enterococci is found in the intestines of warm blooded animals and excreted in faeces and rarely present in unpolluted waters. The bacteria is found in very high numbers in raw sewage which makes it a **good indicator of sewage pollution.**
Studies have shown a strong relationship between elevated levels of enterococci and **illness rates in swimmers.** It's important to note that enterococci doesn't cause illness, but its presence means there's sewage in the water and, therefore, possibly pathogens, which do cause illness.
>
>Indicator organisms are used to test for sewage pollution because:
> - they are easily detectable by simple laboratory tests
> - they are generally not present in unpolluted waters
> - results are available relatively quickly.
>The National health and Medical Research Council (2008) Guidelines for Managing Risks in Recreational Waters recommend enterococci as the single preferred indicator organism for the detection of faecal pollution. 

Check out this picture of enterococci wearing R-Ladies purple!


![](/img/enterococci.jpg)


Ok - back to the lesson...

## 3.2 Read and explore the Sydney beaches data

In this screencast, we'll review:

  * How to read in the beaches into R using `read_csv` and the `here` package 
  * How to get a feel for the data using `View`, `dim`, `str`, `head`, `tail`, and `summary`
  * How to get simple summary stats using the `skimr` package

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/2MVolYETR5Q?rel=0&modestbranding=1" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:

1. Load the `tidyverse` and `here` packages at the top of your script [you should have these there from Lesson 2!]
2. Read the beaches data into R and play around with the summary functions 

Now have a go with **your own data!**

Try putting a datafile that you might need to work with in R in a subfolder of your data folder and use the `here` package to read the data into R. 

What kind of assumptions does R make about the kind of data in each of your columns?


*__Example.__ Here I have made a subfolder called myowndata within my data folder and put a .csv file in it.* 


![](/img/myowndata.png)

*To read it in using the `here` package, just tell R that the data lives in a subfolder.* 

```
kidEMG <- read_csv(here("data", "myowndata", "JustkidCleanEMG.csv")

```


**Sydney-based R-Ladies** - take a screenshot of your own data in R and post it to the #ryouwithme_1_basics Slack channel so we can celebrate your success! [protip: on Mac, command+shift+3 will take a screenshot and save it to your desktop! We're told it's fn+PrtScn on PCs.]

## 3.3 Beyond local CSV files

But what if my data isn't in .csv format?? No problem, there is a package for that! R can read in data from almost anywhere and any format. For example, you can learn more about reading data from...

1. **Excel files**: `install.packages("readxl")` [link](https://readxl.tidyverse.org/)
2. **SPSS/Stata/SAS files**: `install.packages("haven")` [link1](https://haven.tidyverse.org/) [link2](http://www.statscanbefun.com/rblog/2015/8/26/reading-spss-data-into-r)
3. **Google sheets**: `install.packages("googlesheets")` [link](https://cran.r-project.org/web/packages/googlesheets/vignettes/basic-usage.html)
4. **Copy and paste using datapasta**: `install.packages("datapasta")` [link](https://github.com/MilesMcBain/datapasta/blob/master/README.md)

... but R has tools for working with a very wide range of possible data formats and so there are packages out there for all sorts of things. But we'll leave those for a later date.

That's it for [Basic Basics](../01-BasicBasics-1/) (at least for now!). We hope you go and explore RStudio more while you wait for the next [RYouWithMe](../) unit to drop!

### STOP THE PRESS 

> #RYouWithMe now has a data package! Check out https://ryouwithme.netlify.app/ for details about how to install and use the package to read the sydneybeaches data. 


