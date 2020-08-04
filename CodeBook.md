---
title: "CodeBook.md"
author: "Prathmesh Salunkhe"
date: "04/08/2020"
output: word_document
---
##Description
run_analysis.R file takes data and preforms cleaning data.
It returns a cleaned file 'tidy.txt'.

##Assign each data to variables
featureNames <- features.txt
activityLabels <- acivity_labels.txt

subjectTrain <- subject_train.txt
activityTrain <- y_train.txt
featuresTrain <- X_train.txt

subjectTest <- subject_test.txt
activityTest <-y_test.txt
featuresTest <- X_test.txt

subject <- rbind(subjectTrain, subjectTest)
activity <- rbind(activityTrain, activityTest)
features <- rbind(featuresTrain, featuresTest)

colnames(activity) <- "Activity"
colnames(subject) <- "Subject"
completeData <- cbind(features,activity,subject)

##Renaming columns
"Acc"      to  "Accelerometer"
"Gyro"     to  "Gyroscope"
"BodyBody" to  "Body"
"Mag"      to  "Magnitude"
"^t"       to  "Time"
"^f"       to  "Frequency"
"tBody"    to  "TimeBody"
"-mean()"  to  "Mean"
"-std()"   to  "STD"
"-freq()"  to  "Frequency"
"angle"    to  "Angle"
"gravity"  to  "Gravity"

#Result
tidydata.txt  : dim 180*88
column names : 
[1] "Subject"                                           "Activity"                                         
[3] "TimeBodyAccelerometerMean()-X"                     "TimeBodyAccelerometerMean()-Y"                    
[5] "TimeBodyAccelerometerMean()-Z"                     "TimeBodyAccelerometerSTD()-X"                     
[7] "TimeBodyAccelerometerSTD()-Y"                      "TimeBodyAccelerometerSTD()-Z"                     
[9] "TimeGravityAccelerometerMean()-X"                  "TimeGravityAccelerometerMean()-Y"                 
[11] "TimeGravityAccelerometerMean()-Z"                  "TimeGravityAccelerometerSTD()-X"                  
[13] "TimeGravityAccelerometerSTD()-Y"                   "TimeGravityAccelerometerSTD()-Z"                  
[15] "TimeBodyAccelerometerJerkMean()-X"                 "TimeBodyAccelerometerJerkMean()-Y"                
[17] "TimeBodyAccelerometerJerkMean()-Z"                 "TimeBodyAccelerometerJerkSTD()-X"                 
[19] "TimeBodyAccelerometerJerkSTD()-Y"                  "TimeBodyAccelerometerJerkSTD()-Z"                 
[21] "TimeBodyGyroscopeMean()-X"                         "TimeBodyGyroscopeMean()-Y"                        
[23] "TimeBodyGyroscopeMean()-Z"                         "TimeBodyGyroscopeSTD()-X"                         
[25] "TimeBodyGyroscopeSTD()-Y"                          "TimeBodyGyroscopeSTD()-Z"                         
[27] "TimeBodyGyroscopeJerkMean()-X"                     "TimeBodyGyroscopeJerkMean()-Y"                    
[29] "TimeBodyGyroscopeJerkMean()-Z"                     "TimeBodyGyroscopeJerkSTD()-X"                     
[31] "TimeBodyGyroscopeJerkSTD()-Y"                      "TimeBodyGyroscopeJerkSTD()-Z"                     
[33] "TimeBodyAccelerometerMagnitudeMean()"              "TimeBodyAccelerometerMagnitudeSTD()"              
[35] "TimeGravityAccelerometerMagnitudeMean()"           "TimeGravityAccelerometerMagnitudeSTD()"           
[37] "TimeBodyAccelerometerJerkMagnitudeMean()"          "TimeBodyAccelerometerJerkMagnitudeSTD()"          
[39] "TimeBodyGyroscopeMagnitudeMean()"                  "TimeBodyGyroscopeMagnitudeSTD()"                  
[41] "TimeBodyGyroscopeJerkMagnitudeMean()"              "TimeBodyGyroscopeJerkMagnitudeSTD()"              
[43] "FrequencyBodyAccelerometerMean()-X"                "FrequencyBodyAccelerometerMean()-Y"               
[45] "FrequencyBodyAccelerometerMean()-Z"                "FrequencyBodyAccelerometerSTD()-X"   
[47] "FrequencyBodyAccelerometerSTD()-Y"                 "FrequencyBodyAccelerometerSTD()-Z"                
[49] "FrequencyBodyAccelerometerMeanFreq()-X"            "FrequencyBodyAccelerometerMeanFreq()-Y"           
[51] "FrequencyBodyAccelerometerMeanFreq()-Z"            "FrequencyBodyAccelerometerJerkMean()-X"           
[53] "FrequencyBodyAccelerometerJerkMean()-Y"            "FrequencyBodyAccelerometerJerkMean()-Z"           
[55] "FrequencyBodyAccelerometerJerkSTD()-X"             "FrequencyBodyAccelerometerJerkSTD()-Y"            
[57] "FrequencyBodyAccelerometerJerkSTD()-Z"             "FrequencyBodyAccelerometerJerkMeanFreq()-X"       
[59] "FrequencyBodyAccelerometerJerkMeanFreq()-Y"        "FrequencyBodyAccelerometerJerkMeanFreq()-Z"       
[61] "FrequencyBodyGyroscopeMean()-X"                    "FrequencyBodyGyroscopeMean()-Y"                   
[63] "FrequencyBodyGyroscopeMean()-Z"                    "FrequencyBodyGyroscopeSTD()-X"                    
[65] "FrequencyBodyGyroscopeSTD()-Y"                     "FrequencyBodyGyroscopeSTD()-Z"                    
[67] "FrequencyBodyGyroscopeMeanFreq()-X"                "FrequencyBodyGyroscopeMeanFreq()-Y"               
[69] "FrequencyBodyGyroscopeMeanFreq()-Z"                "FrequencyBodyAccelerometerMagnitudeMean()"        
[71] "FrequencyBodyAccelerometerMagnitudeSTD()"          "FrequencyBodyAccelerometerMagnitudeMeanFreq()"    
[73] "FrequencyBodyAccelerometerJerkMagnitudeMean()"     "FrequencyBodyAccelerometerJerkMagnitudeSTD()"     
[75] "FrequencyBodyAccelerometerJerkMagnitudeMeanFreq()" "FrequencyBodyGyroscopeMagnitudeMean()"            
[77] "FrequencyBodyGyroscopeMagnitudeSTD()"              "FrequencyBodyGyroscopeMagnitudeMeanFreq()"        
[79] "FrequencyBodyGyroscopeJerkMagnitudeMean()"         "FrequencyBodyGyroscopeJerkMagnitudeSTD()"         
[81] "FrequencyBodyGyroscopeJerkMagnitudeMeanFreq()"     "Angle(TimeBodyAccelerometerMean,Gravity)"         
[83] "Angle(TimeBodyAccelerometerJerkMean),GravityMean)" "Angle(TimeBodyGyroscopeMean,GravityMean)"         
[85] "Angle(TimeBodyGyroscopeJerkMean,GravityMean)"      "Angle(X,GravityMean)"                             
[87] "Angle(Y,GravityMean)"                              "Angle(Z,GravityMean)"   
