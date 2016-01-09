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
mean(stepsPerDay$total, na.rm = TRUE)
```

```
## [1] 10766.19
```

Median:

```r
median(stepsPerDay$total, na.rm = TRUE)
```

```
## [1] 10765
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
