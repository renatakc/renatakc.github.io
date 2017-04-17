---
layout: post
title:  "Beggining"
date:   2016-03-02 19:32:39
categories: jekyll
---

### Hello, dear readers!

This blog's purpose is to record every point I've learned about programming and data analysis on a daily basis and to have sure I learnt it.

If I grabbed anything from your website, YouTube channel or something related to it and I didn't mention you on this page, please, let me know.

In the morning, I learnt how to extract data from Twitter and Facebook using their API.

For Twitter, they have their API tool (available here: https://apps.twitter.com/), and it is also possible to create your app and link it to Twitter's web page. It is kind of interesting.

This process was made using R and its packages, as TwitteR, TM and Wordcloud.

See the code below for any questions:

```R
consumer_key <- 'XXXXXXXX'

consumer_secret <- 'XXXXXX'
access_token <- 'XXXXXXX'
access_secret <- 'XXXXXX'
library(twitteR)
library(tm)

setup_twitter_oauth(consumer_key, consumer_secret, access_token, access_secret) #set up the connection

# search for keywords

data_science <- searchTwitter("data+science", lang = "en", n = 500, resultType = "recent")

data_sci_text <- sapply(data_science, function(x) x$getText())
str(data_sci_text)

data_sci_corpus <- Corpus(VectorSource(data_sci_text))

data_clean <- tm_map(data_sci_corpus, removePunctuation)

data_clean <- tm_map(data_clean, content_transformer(tolower))
data_clean <- tm_map(data_clean, removeWords, stopwords("english"))
data_clean <- tm_map(data_clean, removeNumbers)
data_clean <- tm_map(data_clean, stripWhitespace)
data_clean <- tm_map(data_clean, removeWords, c("data", "science"))
wordcloud(data_clean)
wordcloud(data_clean, random.order = F, max.words = 50, colors = rainbow(20))
wordcloud(data_clean, random.order = F, max.words = 50)

write.table(data_sci_corpus, "c:/Users/XX/Desktop/data_raw.txt")
```

After that, I also took some data from the Facebook web page, using a tool designed by a German researcher named Till Keyling in 2011 (see the link here: http://www.ls1.ifkw.uni-muenchen.de/personen/wiss_ma/keyling_till/software.html). I used the Facepager to extract the data from a Facebook page and then wrote this code below to run into R, cleaned the data and looked for the most important points.

See the code below:

```R
library(SnowballC)

library(sqldf)

mydata <- read.csv("test_fb.csv", sep = ";") #read csv file

library(tm)

corpus1 <- Corpus(VectorSource(mydata$message)) #create Corpus object
corpus1 <- tm_map(corpus1, tolower, mc.preschedule = FALSE) #convert text to lower case
corpus1 <- tm_map(corpus1, mc.cores=1, removePunctuation)
corpus1 <- tm_map(corpus1, removeNumbers, mc.cores=1)
corpus1 <- tm_map(corpus1, removeWords, stopwords("english"), mc.preschedule = FALSE)
```

However, the most important part of the day comes now.

I connected my SQL database to R-Studio and extracted some raw data from the tables I had stored there. Using the odbcDriverConnect function and the RODBC and the SQLDF packages it becomes so much easier to do this.

Afterwards, you just need to write your query in the right way and run the commands.

Voila, your data will be stored in a variable, and it will be ready to be cleaned and prepared for analysis.

```R
server <- "[server_name].database.windows.net"

user <- "[user]@[server_name]"
password <- "yourpassword"
database <- "YourDatabaseName"
driver <- "YourServer"

connectionString <- paste0("Driver=", driver, 

                           ";server=", server,
                           ";database=", database,
                           ";uid=", user,
                           ";pwd=", password
                           )


conn <- odbcDriverConnect(connectionString)

query <- "SELECT * FROM YourTable"
df <- sqlQuery(conn, query)

close(conn)
```

I took this code from an excellent [web page] that explains how to connect Azure in R and used it as a data source.

I still have work to do, but I am going to finish this content here.

Tomorrow I'll be more hardworking.

Thank you.

P.S.: I took a look at this website to know more about Linear Regression in R: <http://courses.statistics.com/software/R/R_Ch02.htm>.

[web page]: http://blog.revolutionanalytics.com/2015/05/using-azure-as-an-r-datasource.html