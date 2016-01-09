# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
library("dplyr")
library("lubridate")
activity <- read.csv(unz("activity.zip", "activity.csv")) %>% 
    tbl_df %>% 
    mutate(date = ymd(date))
```


## What is mean total number of steps taken per day?
![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)\

Mean:

```r
mean(totalStepsPerDay$total, na.rm = TRUE)
```

```
## [1] 10766.19
```

Median:

```r
median(totalStepsPerDay$total, na.rm = TRUE)
```

```
## [1] 10765
```


## What is the average daily activity pattern?

```r
meanStepsPerInterval <- activity %>% group_by(interval) %>% summarise(average = mean(steps, na.rm = TRUE)) 
with(meanStepsPerInterval, plot(interval, average, type = "l", xlab = "5 minutes interval", ylab = "Average number of steps", lwd = 2))
```

![](PA1_template_files/figure-html/unnamed-chunk-5-1.png)\

Interval containing maximum number of steps:

```r
(meanStepsPerInterval %>% filter(average == max(meanStepsPerInterval$average)))$interval
```

```
## [1] 835
```



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
