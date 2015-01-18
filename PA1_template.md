# Reproducible Research: Peer Assessment 1


**Download data and put it into a data frame** 



```r
fileurl <- "http://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip"
download.file(fileurl, "repdata-data-activity.zip", mode="wb")
unzip("repdata-data-activity.zip")
activity <- read.csv("activity.csv")
```
***What is mean total number of steps taken per day?***


```r
## Total the steps
Total_steps <- aggregate(steps ~ date, data = activity, sum)

## Set labels to variables
MyMainLabel <- "Total steps by day";  MyXLabel <- "Steps per day"; MyYLabel <- "Number of times"

## Show on Histogram
hist(Total_steps$steps, main = MyMainLabel , xlab = MyXLabel, ylab = MyYLabel,col="green")
```

![plot of chunk unnamed-chunk-2](./PA1_template_files/figure-html/unnamed-chunk-2.png) 

**Mean of Total Steps** 


```r
mean(Total_steps$steps)
```

```
## [1] 10766
```

**Median of Total Steps** 


```r
median(Total_steps$steps)
```

```
## [1] 10765
```
