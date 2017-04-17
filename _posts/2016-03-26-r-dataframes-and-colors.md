---
layout: post
title:  "R, dataframes and colors"
date:   2016-03-26 19:32:39
categories: 
---

Hello, everyone!

After two days without posting anything, I was gathering loads of information to post here.
Everybody knows that studying by yourself is hard sometimes because you need to create your plan based on tips you read in websites, talking with professionals and following the common sense. Meanwhile, the best thing about learning by yourself is creating your own agenda. It means you can choose the featured subjects to learn faster than a one-year course, for example.

So, taking a look at Quora.com, I found some good answers to questions, like "What do I need to learn to become a Data Analyst/Scientist?". The best choice option, in my opinion, is the answer below:

1. Master Microsoft Excel
2. Learn Basic SQL
3. Learn Basic Web Development
4. Dive into a Concentration

However, I'd join two more technical skills to this tip: R and Python.
Because, nowadays, as both are free and open-source languages, have loads of packages which can run almost any functionality, most of the companies look for professionals who have good skills in them to join their teams.

Also, I was reading a blog post from a website I like very much (http://www.datasciencecentral.com/profiles/blogs/the-professionalization-of-data-science) and found this phrase, which describes Data Science field:
"The simple truth is that data science is a vast and complicated field and - like law and medicine - much too big and complex for a person to master in one lifetime." - Michael Walker

Well, now I'll show some new R functions I've learnt these last two days (including today).

margin.table
According to R documentation: This is really just apply(x, margin, sum) packaged up for newbies, except that if margin has length zero you get sum(x). (e.g., margin.table(UCBAdmissions))
as.data.frame.table
It's a function to transform your data set in a data frame in a table format. Very useful, by the way. (e.g., admit1 <- as.data.frame.table(UCBAdmissions))

**colors()**

You can see all available colors' names in R to use in any code.

**palette()**

It's just a colors palette with the featured ones.

Another functionality that is very helpful is a package named "RColorBrewer" which description is Creates nice looking color palettes, especially for thematic maps.

**display.brewer.all()**

If you type this function above, it returns a nice colors palette, like this one:


One way to create a great colorful chart is using this feature (brewer.pal) and play with the colors and their colors palettes. For example:

```R
x <- c(12, 4, 21, 17, 13, 9)

barplot(x, col = brewer.pal(6, "Greens"))
barplot(x, col = brewer.pal(6, "YlOrRd"))
barplot(x, col = brewer.pal(6, "RdGy"))
barplot(x, col = brewer.pal(6, "BrBG"))
barplot(x, col = brewer.pal(6, "Dark2"))
barplot(x, col = brewer.pal(6, "Paired"))
barplot(x, col = brewer.pal(6, "Pastel2"))
barplot(x, col = brewer.pal(6, "Set3"))
```

By the way, I mentioned the R-Ladies event I went last Wednesday, but I didn't say anything about it.
As I said last time, it's a meet up for beginners and most of the ladies are novices. We also have some mentors to help in all levels questions, what is great.

Here is link of material we used in the last lesson: http://rpubs.com/crt34/march-workshop-full

In the first half, Chiin explained primary uses of R-Studio, reading .csv files and plotting a graph using ggplot2 and Geo Chart (which allows you plot map graphs).

In the second half, we learnt Clustering + Extension, a Machine Learning technique. I, particularly, didn't understand so much step-by-step, but I knew that studying is part of my every day, then I'll read more about it. Clustering is, in a general way, categorizing the data by its structure.

It is very useful to learn new concepts you have a little knowledge, for example, R language.
I am so grateful people like Chiin exists!

Happy Easter Day!
See ya tomorrow! :)