---
layout: post
title:  "Neo4j what is it"
date:   2016-05-03 19:32:39
categories: 
---

Until yesterday, I had no idea what is the Neo4j technology. Now, I know a bit, because I went to the a hackathon event named GraphHack @ Graph Connect 2016. It was a pre-event to the proper Graph Connect 2016 where people were grouped (not everyone. I, for example, had a group, but we were not able to create a decent model/graph at that moment, so we didn't present anything, but we did try to organise the data and plot the data into a chart). The topic was Travel & Transportation. 

Neo4j is, basically, a graph database which helps you to create relational charts.
A graph database, also called a graph-oriented database, is a type of NoSQL database that uses graph theory to store, map and query relationships. A graph database is essentially a collection of nodes and edges.

The picture below is an excellent example of a network analysis:



It's a chart showing an airport terminal, gates and its venues nearby, like restaurants and other places organised by category. The main benefits of using these graphs are clear visualisation, easier understanding and time and costs reducing in searches.

As I didn't know how to do this using Neo4j, I tried to code in R and plot a network graph, using the data they provided in the event. Here are the results:

![alt text](\static\img\neo4j.png "Neo4j")

Tcharam! There is a network chart!
It was made using a simple example which I found on a very informative website. You can get the R code below:

setwd("C:/Users/Re/Documents/Neo4j")

library(network) 
library(sna)
library(ndtv)
library(igraph)

nodes <- read.csv("Dataset1-Media-Example-NODES.csv", header=T, as.is=T)
links <- read.csv("Dataset1-Media-Example-EDGES.csv", header=T, as.is=T)

nrow(nodes); length(unique(nodes$id))
nrow(links); nrow(unique(links[,c("from", "to")]))

links <- aggregate(links[,3], links[,-3], sum)
links <- links[order(links$from, links$to),]
colnames(links)[4] <- "weight"
rownames(links) <- NULL

net <- graph.data.frame(links, nodes, directed=T)

plot(net)

net <- simplify(net, remove.multiple = F, remove.loops = T)
plot(net, edge.arrow.size=.4,vertex.label=NA)

This code allows you to create that chart above, which is precious to visualise network connections into the data.

Lately, I'd been very busy but, I know that writing at least three or four times in the week is important to study and practice vocabulary.

That's all! Thank you and see you tomorrow!

Sources:
http://neo4j.com/developer/graph-database/
http://graphconnect.com/
http://kateto.net/network-visualization