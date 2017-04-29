---
layout: post
title:  "Simple charts"
date:   2016-03-13 19:32:39
categories: 
---

Finally, I am getting better! I was so sick that I couldn't even open my eyes to write in this Blog (Yes, this is true!). My head was hurting so much that I was wondering when I could get off the bed and do not fall just to standing on feet or feeling sick just to taking a shower. Horrible flu!

Today, in the last hours I've been tried to build some charts and had some insights from them.

The first data set I analyzed was Big Mac Index, from January 2016.
See below the code I used:

```R
# set work directory
setwd("C:/Users/Re/Documents/R")

# read the .csv file and choose header or don't
bigmacindex <- read.csv("BigMacIndex.csv", header = TRUE)

# here, I chose just two columns to analyse: 1 and 4
BigMacIndex <- bigmacindex[,c(1,4)]

# create a matrix and transpose it
d<-as.matrix(t(BigMacIndex))

# create the bar chart with title, Y axis name and X labels
barplot(BigMacIndex$dollar_price, names.arg = BigMacIndex$Country, las = 2, 
        main = "Big Mac Index - Jan 16",
        ylab = "US$ dollar")
```
 


The second created chart was by using data from here http://ec.europa.eu/eurostat/web/main/home.

First of all, I needed to clean the data, select just the columns which contain the essential data and then start building the chart.

Unfortunately, I could not create the table (and I still don't know why), but I'll try it again and post here asap!


