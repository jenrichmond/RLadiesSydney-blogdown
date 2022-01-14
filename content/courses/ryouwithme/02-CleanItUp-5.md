---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: ""
menu:
  ryouwithme:
    parent: CleanItUp
    weight: 6
title: CleanItUp 5
toc: true
type: docs
weight: 3
---

# Wide to Long to Wide to...PIVOT

Learning how to make wide data long, or long data wide, might be one of the biggest stumbling blocks that R learners encounter. Even Rlady ed experts like [Jesse Mostipak](https://twitter.com/kierisi) freely admit to not really "getting it". 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">there&#39;s a pretty large discrepancy between how well I *think* I know spread() and gather() and how well I *actually* know spread() and gather() </p>&mdash; Jesse Mostipak (@kierisi) <a href="https://twitter.com/kierisi/status/1056637253483720704?ref_src=twsrc%5Etfw">October 28, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


But don't panic, there are NEW functions in the `tidyr` that make the process of converting your data from wide to long format and back again, much easier... so much so that, like RLady [Sharla Gelfand](@sharlagelfand), you might even get excited to do it!

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">honestly i used to dread having to reshape my data because it meant relearning spread() and gather() every single time but pivot_wider() and pivot_longer() are so easy to use that now i get excited when i have to do it 🤓</p>&mdash; Sharla Gelfand (@sharlagelfand) <a href="https://twitter.com/sharlagelfand/status/1252656466852548608?ref_src=twsrc%5Etfw">April 21, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


### Why do you need to know how to convert your data from wide to long (or vice versa)?

In R circles there is a lot of talk of the need for "tidy data". You can read more about what Hadley Wickham (creator of the Tidyverse) means by [tidy data here](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html), but in short, tidy data is when

1. Each variable forms a column.
2. Each observation forms a row.
3. Each type of observational unit forms a table.

When you entered your data in excel, you probably entered it in wide format. Data in wide format has observations spread across several columns; each column contains data from a different condition (or combination of conditions). wide data is messy. 

In the wide example below, we have scores from participants who were tested twice (Time 1 and Time 2) after studying different lists of words under two different conditions (Condition 1 and Condition 2). 


![](/img/2_wideexample.png)


In contrast, data in long format has all the observations in a single column and variables in separate columns. 


![](/img/1_longexample.png)


### Should I could copy and paste_transpose the scores?

No, no, no... this is not as hard as it looks. R employs cute monsters under the hood to pivot your data from wide to long `pivot_longer`, or from long to wide `pivot_wider`. All in a single line of code. 

![](/img/pivot_monsters.png)

Credit to [Allison Horst](https://twitter.com/Allison_Horst) for the CUTE art. 

In this lesson, we will use three different examples to illustrate how to use `pivot_longer` and `pivot_wider` to convert your data from wide to long and back to wide. 

1. Great British Bakeoff data from [Alison Hill](https://twitter.com/apreshill)
2. Some summary data from our own sydneybeaches dataset
3. A tricky example from a cognition experiment out of [Dani Navarro's](https://twitter.com/djnavarro) lab

### STOP THE PRESS 

> #RYouWithMe now has a data package! Check out https://ryouwithme.netlify.app/ for details about how to install and use the package to read the bakers, beach summary and frames data.

Each example is a little different, but in each case we can use `pivot_longer` and `pivot_wider` to switch between different formats. We'll walk you through the process step by step, but the basic idea is shown graphically in this lovely animation made by [Garrick Aden-Buie](https://twitter.com/grrrck) and adapted by [Mara Averick](https://twitter.com/dataandme).


![](/img/tidyr-longer-wider.gif)



### Example 1: which bakers can identify spices?

Thanks to [Alison Hill](https://twitter.com/apreshill) for sharing this example. This data is from a Great British Bakeoff challenge; I assume that bakers were tested on their ability to identify different spices. 

The dataframe on the left is in wide format; the performance of each baker in each spice test is listed across different columns. 

![](/img/pivot_longer_data.png)
Image credit: [Alison Hill](https://twitter.com/apreshill)


The dataframe on the right is in long format; all of the accuracy scores are in a single column and information about which baker and spice test each observation came from are represented in separate variables.


#### Using `pivot_longer` (wide to long)

The `pivot_longer` function will change your wide data to long format in a single line of code. 

You need to tell it ...

-  data= dataframe you want to pivot
-  names_to = name of column you want to create to capture condition (i.e. spice)
-  values_to = name of column you want to contain data values (i.e. correct)
-  column X:column Y = range of columns that you have and want to pivot_longer (cinnamon_1:nutmeg_3)

![](/img/longer_arguments.png)
Image credit: [Alison Hill](https://twitter.com/apreshill)



#### Using `pivot_wider` (long to wide)

The `pivot_wider` function will change your long data to wide format in a single line of code. 

You need to tell it ...

-  data = dataframe you want to pivot
-  names_from = name of column you want to end up in several columns 
-  values_from = name of column that currently contains data values

![](/img/wider_arguments.png)
Image credit: [Alison Hill](https://twitter.com/apreshill)



#### Your turn: Challenge 1 

Here is a link to the [bakers data in wide format](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/bakers_wide.csv).

- download the [data](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/bakers_wide.csv) and put it in your data folder
- open a new script
- load the tidyverse and here packages
- use `here` and `read_csv` to read the bakers data (go back to Basic Basics if you've forgotten how this works)
- use `pivot_longer` to convert the bakers data from wide to long, replicating Alison's steps above. 



### Example 2: long beaches are better than wide 

The raw sydneybeaches data is helpfully already in long format, but I have created a couple of summary datasets so we can practice changing data from wide to long and back again.

In the wide format, I've averaged bug levels for each year and the beach sites appear in separate columns. 


![](/img/8_wide_beaches.png)



In long format, the bug levels from each site are all in a single column and year and site are represented as separate variables. 



![](/img/7_long_beaches.png)



#### Your turn: Challenge 2
Here is a link to the [beaches summary in wide format](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/beachbugs_wide.csv)

- download the [data]((https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/beachbugs_wide.csv)) and put it in your data folder
- open a new script
- load library tidyverse 
- use `here` and `read_csv` to read the beaches data (go back to Basic Basics if you've forgotten how this works)
- use `pivot_longer` to convert the beaches data from wide to long

In this screencast, I walk you through how to use `pivot_longer` to make the wide beaches data long.  

<iframe width="560" height="315" src="https://www.youtube.com/embed/vu_ePf3sA1E" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



In this one, learn how to use `pivot_wider` to make long beaches data wide. 


<iframe width="560" height="315" src="https://www.youtube.com/embed/vcy_S1HIG7c" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



### Example 3: A tricky one

The bakers data and beaches data are relatively simple. What happens if there is more that one condition that you are trying to pivot across? 

This sampling frames dataset comes from an experiment from [Dani Navarro's](https://twitter.com/djnavarro) lab. In this study, each participant made reasoning judgements about items either based on a category or property (condition). They made repeated judgements after being given a small, medium, and large "samples" of information. For each of these sampling conditions, there were 7 different items that participants made a judgement about.  

Here is what the data looks like in wide format. 

![](/img/frames_wide.png)



Each row contains all of the data from a single participant and the column represent information about BOTH sampling condition (small, medium, large) and item (1-7). 


#### Your turn: Challenge 3.1 

Here is a link to the [frames data in wide format](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/frames_wide.csv).

- download the [data](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/frames_wide.csv) and put it in your data folder
- open a new script
- load the tidyverse and here packages
- use `here` and `read_csv` to read the frames data (go back to [Basic Basics](../01-BasicBasics-3/) if you've forgotten how this works)
- use `pivot_longer` to convert the frames data from wide to long


### How did you go?

Hopefully you ended up with a data frame that looks something like this.

![](/img/frames_final.png)


If not, check out how you can add an extra argument to pivot_longer() and accomplish this pivot in a single step. 


<iframe width="560" height="315" src="https://www.youtube.com/embed/GhVweI0MRUg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Your turn: Try your own data

Is your data in wide format? No problem. Sort out answers to the following questions and you can convert it to long format with a single line of code. 

1. What do you want your "names" column to be called? 
2. What are the "values"?
3. Which columns do you want to pivot? 

**Sydney-based R-Ladies** - share your successes and any challenges you've faced in the #ryouwithme_2_cleaning Slack channel! 



### Looking for more?

Some additional links that might be helpful!

- [What is tidy data?](https://github.com/gadenbuie/tidyexplain#tidy-data)
- [Pivoting tidily](https://fromthebottomoftheheap.net/2019/10/25/pivoting-tidily/)
- [TidyR docs](https://tidyr.tidyverse.org/)
- [TidyTuesday pivot examples](https://thatdatatho.com/2020/03/28/tidyrs-pivot_longer-and-pivot_wider-examples-tidytuesday-challenge/) 
