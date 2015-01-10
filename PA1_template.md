# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
#load the data
activityData <- read.csv(unz("activity.zip", "activity.csv"), stringsAsFactors=FALSE)
#transform the date column from string to date
activityData$date <- as.Date(activityData$date, '%Y-%m-%d')
```

## What is mean total number of steps taken per day?
1. Make a histogram of the total number of steps taken each day

```r
activityDataByDate <- aggregate(activityData$steps, list(date = activityData$date), sum)
hist(activityDataByDate$x, xlab = "total number of steps", main = "Histogram of total number steps by date")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

2. Calculate and report the mean and median total number of steps taken per day

```r
mean(activityDataByDate$x, na.rm = TRUE)
```

```
## [1] 10766.19
```

```r
median(activityDataByDate$x, na.rm = TRUE)
```

```
## [1] 10765
```

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
