---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: ""
menu:
  ryouwithme:
    parent: CleanItUp
    weight: 3
title: CleanItUp 2
toc: true
type: docs
weight: 3
---

# Exploring the Rows

Now that we have cleaned up our column names to make them easier to work with, we can start to answer some questions about what's in those rows! In this lesson, we’re going to `filter`, `arrange`, `group_by` and `summarise` the beaches data to answer the following questions:   

- **Question A:** Which beach has the highest recorded bacteria levels?
- **Question B:** Does Coogee or Bondi have more extreme bacteria levels? Which beach has the worst bacteria levels on average?
- **Question C:** Which council does the worst job at keeping their beaches clean?

## Lesson Outcomes
By the end of the lesson, you should:

- 2.1 Know how to use `arrange` to sort a dataframe and `filter` to select parts of the - 2.2 Know how to use `group_by` and `summarise` to get summary statistics
- 2.3 Be able to pipe these functions together to answer questions about your data

## Question A: Which beach has the highest recorded bacteria levels?

When we first looked at a `summary` of the sydneybeaches data, we could see that the highest value of beach bacteria in the dataset was 4900. I wonder which beach that came from? Here, we use `arrange` to sort the beach bugs data in descending order. We can also use the pipe to combine `filter` and `arrange` to look at extreme values within a particular site. 

![](/img/clean2-summary.png)


In this screencast, we’ll review:

  * How to use the `arrange` function to sort your data
  * How to use `filter` to look at just a subset of your data
  * How to use the pipe to combine `filter` and `arrange` functions


<iframe width="560" height="315" src="https://www.youtube.com/embed/nJIB643YETo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:  

1. Sort the sydney beaches data by beachbugs in descending order
2. Pick your favourite beach and determine whether its most extreme beachbug values are higher or lower than the worst day at Coogee. 

## Question B: Does Coogee or Bondi have more extreme bacteria levels? Which beach has the worst bacteria levels on average?

"Where should I swim?" you might ask… Well, to answer that question we need to compare bacteria levels across sites. 

To do this, uou can put more than one argument into a filter function. For example, you can filter for either Coogee or Bondi. 

In this screencast, we’ll review:

  * How to use `filter` by more than one site 
  * How to create grouped summary stats using `group_by` and `summarise`
  * How to use the pipe to combine `filter`, `group_by`, and `summarise` functions

<iframe width="560" height="315" src="https://www.youtube.com/embed/m0735DnMry8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Watch the video and then carry out the following steps:  

1. Pick two beaches to compare, use filter and the %in% operator
2. Use group_by and summarise to work out which beach has the worst bacteria levels on average. 

## Question C: Which council does the worst job at keeping their beaches clean?

Lets practice our new `dplyr` skills, using `group_by` council (instead of site) and `summarise` to see which council does the best job at keeping its beaches clean. 

In this screencast, we’ll review:  

  * How to `group_by` more multiple variables to gain more insight into the summary statistics from `summarise`
  * How to assign the output of your `summarise` to a new object in your environment 


<iframe width="560" height="315" src="https://www.youtube.com/embed/w6lyT6YyycE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Now have a go with **your own data!**

- Choose a continuous variable and sort your data in descending order. Are the extreme values surprising?
- Pick a categorical variable, filter for one level of that variable and then sort in descending order
- Use group_by and summarise to create summary statistics that answer a question you have about your data

**Sydney-based R-Ladies** - share your successes and any challenges you've faced in the #ryouwithme_2_cleaning Slack channel! 

Next up - Clean It Up [Lesson 3: Making New Variables](../02-CleanItUp-3/))

### P.S. Interested in more `dplyr` tutorials?
Check out this blog series by R-Lady Suzan Baert! 

- [Selecting](https://suzan.rbind.io/2018/01/dplyr-tutorial-1/)
- [Filtering](https://suzan.rbind.io/2018/02/dplyr-tutorial-3/#filtering-based-on-a-exact-character-variable-matches) 
- [Summarising](https://suzan.rbind.io/2018/04/dplyr-tutorial-4/)


