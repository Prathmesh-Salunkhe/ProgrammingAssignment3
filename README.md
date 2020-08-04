---
title: "README"
author: "Prathmesh Salunkhe"
date: "03/08/2020"
output: word_document
---

## Data link 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

extract the file in the folder 

##Tasks performed
1) Merges the training and the test sets to create one data set.
2) Extracts only the measurements on the mean and standard deviation for each measurement.
3) Uses descriptive activity names to name the activities in the data set
4) Appropriately labels the data set with descriptive variable names.
5) From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

##Content
This Project contains run_analysis.R which processes the data and returns a file 'tidy.txt'.
This Project contains CodeBook.md which describes the data and the processes.

## Cleaning data

Reading data using read.table function
row binding train and test
column binding subject,feature and activity

getting columns with mean and std
changing col names to become more understandable

putting into a file tidy.txt