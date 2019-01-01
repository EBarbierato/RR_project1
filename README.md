Reproducible Research Week2 Project 1
Enrico Barbierato

January 1, 2019

R Markdown
Introduction

It is now possible to collect a large amount of data about personal movement using activity monitoring devices such as a Fitbit, Nike Fuelband, or Jawbone Up. These type of devices are part of the “quantified self” movement - a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. But these data remain under-utilized both because the raw data are hard to obtain and there is a lack of statistical methods and software for processing and interpreting the data.

This assignment makes use of data from a personal activity monitoring device. This device collects data at 5 minute intervals through out the day. The data consists of two months of data from an anonymous individual collected during the months of October and November, 2012 and include the number of steps taken in 5 minute intervals each day.

The data for this assignment can be downloaded from the course web site:

Dataset: Activity monitoring data [52K] The variables included in this dataset are:

steps: Number of steps taking in a 5-minute interval (missing values are coded as NA) date: The date on which the measurement was taken in YYYY-MM-DD format interval: Identifier for the 5-minute interval in which measurement was taken The dataset is stored in a comma-separated-value (CSV) file and there are a total of 17,568 observations in this dataset.

  library(ggplot2)
Load the data (i.e. read.csv()) Process/transform the data (if necessary) into a format suitable for your analysis

  df <- read.csv("activity.csv", as.is = TRUE)
  df_not_NA <- na.omit(df)
What is mean total number of steps taken per day? For this part of the assignment, you can ignore the missing values in the dataset.

Calculate the total number of steps taken per day If you do not understand the difference between a histogram and a barplot, research the difference between them. Make a histogram of the total number of steps taken each day

  total_steps_per_day<-aggregate(steps ~ date, df, sum)
  hist(total_steps_per_day$steps, main = "Total number of steps per day", xlab = "Steps per day")
