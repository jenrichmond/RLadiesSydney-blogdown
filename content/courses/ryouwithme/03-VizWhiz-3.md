---
date: "2019-05-05T00:00:00+01:00"
draft: false
linktitle: "VizWhiz 3"
menu:
  ryouwithme:
    parent: VizWhiz
    weight: 4
title: VizWhiz 3
toc: true
type: docs
weight: 4
---

The `ggplot` fanciness we covered in [Lesson 1](../03-VizWhiz-1/) and [Lesson 2](../03-VizWhiz-2/) is great, but sometimes your boss/grant agency/publication outlet insists on a bar or column graph. Or perhaps you simply need to visualise two continuous variables. In this lesson, we will show you how to plot bar and column graphs with error bars and how to plot a scatter plot. 

## Lesson Outcomes

By the end of the lesson, you should:

* 3.1 Understand the difference between  `geom_bar` and `geom_col` and use them to plot frequency vs. summary data 
* 3.2 Be able to use `summarise` to calculate standard error and `geom_errorbar` to add error bars to a plot
* 3.3 Be able to use `geom_point` to create a scatter plot of two continuous variables 

# 3.1 Bars vs. columns

There are two geoms in ggplot that draw bar plots, `geom_bar`and `geom_col`. 

When you want to plot frequency/count data and are happy to let R to do the counting autoamtically, use `geom_bar`. It only requires that you tell it what you want on the x axis, and it will put frequency on the y axis. 

If you want the height of the bar to represent a value you have calculated, then use `geom_col`. For this geom, you need to tell it what you want for both the x axis and the y axis.  

In this screencast, we’ll review:

  * How to use `geom_bar` to plot count/frequency data
  * How to combine `summarise` and `geom_col` to plot mean bug levels by year
  * How to `group_by` more than one variable and use `facet_wrap` to plot mean bug levels by year, separately for each site

<center>  
<iframe width="560" height="315" src="https://www.youtube.com/embed/qijh53hQEt8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>  

Here's the plot for reference:


![](/img/col_meanbugs.png)

Watch the video and then carry out the following steps:

1. Use `geom_bar` and `facet_wrap` to plot the number of readings that were taken each year, separately for each site
2. Use `group_by` and `summarise` with `geom_col` to plot the mean beach bug levels averaged across all the sites each year
3. Use `group_by` and `summarise` with `geom_col` to plot the mean beach bug levels each year, using `facet_wrap` to plot each site separately

# 3.2 Error bars

Of course, good practice dictats that you need error bars on those columns. Never fear! Using `summarise`, it is easy to calculate standard error. 

In this screencast, we’ll review:

  * How to use `summarise` to calculate the mean, standard deviation and standard error
  * How to add a `geom_errorbar` layer to your plot to display the mean beach bugs data in a column graph with error bars

<center>  
<iframe width="560" height="315" src="https://www.youtube.com/embed/vlA8GpuuDcw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>  

Here's the plot for reference:

![](/img/col_meanbugs_error.png)

Watch the video and then carry out the following steps:

1. Use `group_by` and `summarise` to calculate the mean, standard deviation, N, and standard error for each site 
2. Pipe that `summarise` into a `geom_col` adding a `coorid_flip` and `geom_errorbar` layer

# 3.3 Scatter plots 

Sometimes you want to visualise the relationship between two continuous variables using a scatterplot. Our original beachbugs dataset doesn't include any interesting variables that might be correlated with the bacteria levels, so we have pulled in some weather data to see whether bacteria levels might be related to rainfall or temperature, or some combination of the two. 

You can download the rain_temp_beachbugs.csv data [here](https://github.com/jenrichmond/RLadiesSydney-blogdown/blob/master/csv/rain_temp_beachbugs.csv) 

### STOP THE PRESS 

> #RYouWithMe now has a data package! Check out https://ryouwithme.netlify.app/ for details about how to install and use the package to read the bakers, beach summary and frames.  

In this screencast, we’ll review:

  * How to import the rain_temp_beachbugs.csv dataset into R
  * How to use `geom_point` and `geom_smooth` to plot a scatter plot and best fit line
  * How to use point color to illustrate potential interactions in your data 

<center>  
<iframe width="560" height="315" src="https://www.youtube.com/embed/Ouoinu4ScPs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>  


Here's the plot for reference:

![](/img/scatter_rain_temp.png)

Watch the video and then carry out the following steps:

1. use `read_csv` and `here` to read the rain_temp data into RStudio (need help? revisit [Unit 1 Basic Basics Lesson 3: Loading Data](https://rladiessydney.netlify.com/courses/workshop/01-basicbasics-3/) 
2. use `geom_point` to plot the relation between rainfall and beach bugs 
3. `filter` the data for values more than 500 and add a `geom_smooth` layer to see a regression line
4. colour the points by the temperature variable

### Now it's your turn!

Are bar plots your bread and butter? Or maybe you primarily work with bivariate continuous data? Either way, we want to see your plots! Tweet them to us at @RLadiesSydney using the hashtag: #vizwhiz!

Sydney-based RLadies are encouraged to share your successes, frustrations, and of course your plots, in our slack channel, #ryouwithme_3_vizwhiz. 

Now that you've got the structural components of several of the most popular plots down, it's time to learn how to customise the appearance of those plots! Onward to [Lesson 4](../03-VizWhiz-4/!
