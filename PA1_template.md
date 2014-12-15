---
title: "Reproducible Research: Peer Assessment 1"
output: html_document

---

**Load Data** 

```{r}
activity <- read.csv("activity.csv")
```
***What is mean total number of steps taken per day?***

```{r}
## Total the steps
Total_steps <- aggregate(steps ~ date, data = activity, sum)

## Set labels to variables
MyMainLabel <- "Total steps by day";  MyXLabel <- "Steps per day"; MyYLabel <- "Number of times"

## Show on Histogram
hist(Total_steps$steps, main = MyMainLabel , xlab = MyXLabel, ylab = MyYLabel,col="green")
```

**Mean of Total Steps** 

```{r}
mean(Total_steps$steps)
```

**Median of Total Steps** 

```{r}
median(Total_steps$steps)
```


