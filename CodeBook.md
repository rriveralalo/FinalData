## CodeBook: Data Science Specialization course series: Getting and Cleaning Data Course Project

============================================================================================
### Original raw data sets: Human Activity Recognition Using Smartphones Dataset Version 1.0:

Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws

A full description is available at the site www.smartlab.ws where the data was obtained: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

-------------------------------------------------------------------------------------------------
#### List of the original data sets inside the downloaded zip file:

 	 - 'README.txt': describes about the general information and background related to the data sets within the zip file.
	
 	 - 'features_info.txt': Shows information about the variables used on the feature vector.

   	 - 'features.txt': List of all features.

   	 - 'activity_labels.txt': Links the class labels with their activity name.

   	 - 'train/X_train.txt': Training set.

   	 - 'train/y_train.txt': Training labels.

   	 - 'test/X_test.txt': Test set.

   	 - 'test/y_test.txt': Test labels.
   
    	 - 'train/subject_train.txt':   Each row identifies the subject who performed the activity for each window sample.
            Its range is from 1 to 30. (for training set)
   
  	 - 'test/subject_test.txt':  Each row identifies the subject who performed the activity for each window sample.
  	    Its range is from 1 to 30. (for test set)
      
   	  The following data sets are not been used in the current project. 

   	 - 'train/Inertial Signals/total_acc_x_train.txt'; 'train/Inertial Signals/body_acc_x_train.txt';
   	   'train/Inertial Signals/body_gyro_x_train.txt'. More information related to these three data sets can be
   	    found in 'README.txt', 'feature_info.txt' and 'feature.txt' and the original website.
    
-------------------------------------------------------------------------------------------------------------
#### Background: feature selection, feature vector variables and unit

The following information is the hightlights/summary of the 'feature_info.txt' and 'feature.txt'

>The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years.
>Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING)
>wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope,
>they captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz.
>The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly
>partitioned into two sets, where 70% of the volunteers was selected for generating the training data
>and 30% the test data.
>
>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ 
>and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. 
>Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency
>of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration
>signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
>
>Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals
>(tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated 
>using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
>
>Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ,
>fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. 
>(Note the 'f' to indicate frequency domain signals). 

>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>		tBodyAcc-XYZ
>		tGravityAcc-XYZ
>		tBodyAccJerk-XYZ
>		tBodyGyro-XYZ
>		tBodyGyroJerk-XYZ
>		tBodyAccMag
>		tGravityAccMag
>		tBodyAccJerkMag
>		tBodyGyroMag
>		tBodyGyroJerkMag
>		fBodyAcc-XYZ
>		fBodyAccJerk-XYZ
>		fBodyGyro-XYZ
>		fBodyAccMag
>		fBodyAccJerkMag
>		fBodyGyroMag
>		fBodyGyroJerkMag
>
>	Additional vectors obtained by averaging the signals in a signal window sample. 
>	These are used on the angle() variable:
>
>		gravityMean
>		tBodyAccMean
>		tBodyAccJerkMean
>		tBodyGyroMean
>		tBodyGyroJerkMean
>
>	The set of variables that were estimated from these signals are: 
>
>		mean(): Mean value
>		std(): Standard deviation
>		mad(): Median absolute deviation 
>		max(): Largest value in array
>		min(): Smallest value in array
>		sma(): Signal magnitude area
>		energy(): Energy measure. Sum of the squares divided by the number of values. 
>		iqr(): Interquartile range 
>		entropy(): Signal entropy
>		arCoeff(): Autorregresion coefficients with Burg order equal to 4
>		correlation(): correlation coefficient between two signals
>		maxInds(): index of the frequency component with largest magnitude
>		meanFreq(): Weighted average of the frequency components to obtain a mean frequency
>		skewness(): skewness of the frequency domain signal 
>		kurtosis(): kurtosis of the frequency domain signal 
>		bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
>		angle(): Angle between to vectors.

##### Unit:

Features are normalized and bounded within [-1,1]. In other words, they are unitless.

------------------------------------------------------------------------------------------------
#### Original data sets: selected input data variables

Based on the requirement of the course project, I only selected those input variables
related to the measurements on the mean and standard deviation for each measurement.
(see the section of "Instruction and Requirements" in README.md)

They are the following:

	tBodyAcc-mean()-X           tBodyAcc-mean()-Y           tBodyAcc-mean()-Z           tBodyAcc-std()-X           
	tBodyAcc-std()-Y            tBodyAcc-std()-Z            tGravityAcc-mean()-X        tGravityAcc-mean()-Y       
	tGravityAcc-mean()-Z        tGravityAcc-std()-X         tGravityAcc-std()-Y         tGravityAcc-std()-Z        
	tBodyAccJerk-mean()-X       tBodyAccJerk-mean()-Y       tBodyAccJerk-mean()-Z       tBodyAccJerk-std()-X       
	tBodyAccJerk-std()-Y        tBodyAccJerk-std()-Z        tBodyGyro-mean()-X          tBodyGyro-mean()-Y         
	tBodyGyro-mean()-Z          tBodyGyro-std()-X           tBodyGyro-std()-Y           tBodyGyro-std()-Z          
	tBodyGyroJerk-mean()-X      tBodyGyroJerk-mean()-Y      tBodyGyroJerk-mean()-Z      tBodyGyroJerk-std()-X      
	tBodyGyroJerk-std()-Y       tBodyGyroJerk-std()-Z       tBodyAccMag-mean()          tBodyAccMag-std()          
	tGravityAccMag-mean()       tGravityAccMag-std()        tBodyAccJerkMag-mean()      tBodyAccJerkMag-std()      
	tBodyGyroMag-mean()         tBodyGyroMag-std()          tBodyGyroJerkMag-mean()     tBodyGyroJerkMag-std()     
	fBodyAcc-mean()-X           fBodyAcc-mean()-Y           fBodyAcc-mean()-Z           fBodyAcc-std()-X           
	fBodyAcc-std()-Y            fBodyAcc-std()-Z            fBodyAccJerk-mean()-X       fBodyAccJerk-mean()-Y      
	fBodyAccJerk-mean()-Z       fBodyAccJerk-std()-X        fBodyAccJerk-std()-Y        fBodyAccJerk-std()-Z       
	fBodyGyro-mean()-X          fBodyGyro-mean()-Y          fBodyGyro-mean()-Z          fBodyGyro-std()-X          
	fBodyGyro-std()-Y           fBodyGyro-std()-Z           fBodyAccMag-mean()          fBodyAccMag-std()          
	fBodyBodyAccJerkMag-mean()  fBodyBodyAccJerkMag-std()   fBodyBodyGyroMag-mean()     fBodyBodyGyroMag-std()     
	fBodyBodyGyroJerkMag-mean() fBodyBodyGyroJerkMag-std() 

The complete list of variables of each feature vector is available in 'features.txt'

  
-------------------------------------------------------------------------------------------------------------
#### Tidy data set: data structure

* There are 180 observations of 88 variables.

		'data.frame':	180 obs. of  88 variables:
		 $ activity                 : chr  
		 $ subject                  : int  
		 $ tbodyacc.mean.x          : num 
		 $ tbodyacc.mean.y          : num  
		 $ tbodyacc.mean.z          : num  
		 $ tbodyacc.std.x           : num  
		 $ tbodyacc.std.y           : num 
 		 $ tbodyacc.std.z           : num  
		 $ tgravityacc.mean.x       : num   
		 $ tgravityacc.mean.y       : num  
		 $ tgravityacc.mean.z       : num   
		 $ tgravityacc.std.x        : num  
		 $ tgravityacc.std.y        : num  
		 $ tgravityacc.std.z        : num  
		 $ tbodyaccjerk.mean.x      : num  
		 $ tbodyaccjerk.mean.y      : num 
 		 $ tbodyaccjerk.mean.z      : num  
		 $ tbodyaccjerk.std.x       : num  
		 $ tbodyaccjerk.std.y       : num  
		 $ tbodyaccjerk.std.z       : num  
		 $ tbodygyro.mean.x         : num  
		 $ tbodygyro.mean.y         : num  
		 $ tbodygyro.mean.z         : num  
		 $ tbodygyro.std.x          : num  
		 $ tbodygyro.std.y          : num  
		 $ tbodygyro.std.z          : num  	 
		 $ tbodygyrojerk.mean.x     : num  
		 $ tbodygyrojerk.mean.y     : num  
		 $ tbodygyrojerk.mean.z     : num  
		 $ tbodygyrojerk.std.x      : num  
		 $ tbodygyrojerk.std.y      : num  
		 $ tbodygyrojerk.std.z      : num  
		 $ tbodyaccmag.mean         : num  
		 $ tbodyaccmag.std          : num  
		 $ tgravityaccmag.mean      : num  
		 $ tgravityaccmag.std       : num  
		 $ tbodyaccjerkmag.mean     : num  
 		 $ tbodyaccjerkmag.std      : num  
 		 $ tbodygyromag.mean        : num  
		 $ tbodygyromag.std         : num  
		 $ tbodygyrojerkmag.mean    : num  
		 $ tbodygyrojerkmag.std     : num  
		 $ fbodyacc.mean.x          : num   
		 $ fbodyacc.mean.y          : num  
		 $ fbodyacc.mean.z          : num  
		 $ fbodyacc.std.x           : num  
		 $ fbodyacc.std.y           : num  
		 $ fbodyacc.std.z           : num  
		 $ fbodyaccjerk.mean.x      : num  
		 $ fbodyaccjerk.mean.y      : num  
		 $ fbodyaccjerk.mean.z      : num  
		 $ fbodyaccjerk.std.x       : num  
		 $ fbodyaccjerk.std.y       : num  
 		 $ fbodyaccjerk.std.z       : num  
		 $ fbodygyro.mean.x         : num  
		 $ fbodygyro.mean.y         : num  
		 $ fbodygyro.mean.z         : num  
		 $ fbodygyro.std.x          : num  
		 $ fbodygyro.std.y          : num  
		 $ fbodygyro.std.z          : num  
		 $ fbodyaccmag.mean         : num  
		 $ fbodyaccmag.std          : num  
		 $ fbodybodyaccjerkmag.mean : num  
		 $ fbodybodyaccjerkmag.std  : num  
		 $ fbodybodygyromag.mean    : num  
		 $ fbodybodygyromag.std     : num  
		 $ fbodybodygyrojerkmag.mean: num  
		 $ fbodybodygyrojerkmag.std : num  
 
---------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------
### Study Design Summary
 
 * How to collect the data
 
   This is a course project. The location of this original raw data set for this course project 
   is provided via the link (see the section of Data Resources in README.md)
   https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
   
   
 * The purposes/goal of this study design
 
   The first priority of this study design is fulfiled  all the purposes and requirements
   of this project (see the sections of "Purpose and Goal" and "Instructions and Requirements")
   in README.md.
 
---------------------------------------------------------------------------------------
### Instruction list to reproduce the tidy data set

This section is also in the section of "My work to the project" in README.md

#### Obtain the raw data sets and put them in the working directory (via Rstudio)
Download the raw data from the following website: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Upload file from computer to File pane in RStudio Posit Cloud. Set this file as working directory. > setwd("/cloud/project") Create a tidy data via a R script called run_analysis.R Preparation: data sets and script

The data sets and run_analysis.R must be in the working directory. It is based on one of the requirements this project: The code should have a file run_analysis.R in the main directory that can be run as long as the Samsung data is in your working directory. (see "Instructions and Requirements")
 
    
#### Create a tidy data via a R script called run_analysis.R
      
There are 6 main steps in run_analysis.R to process the raw data sets and create the tidy data set.

Step-0: Reminder -- to install special package "dplyr". It is necessary to install and to load the package "dplyr" before to perform any processes.

Step-1: Assigning all data frames

features <- read.table("UCI HAR Dataset/features.txt", col.names = c("n","functions")) activities <- read.table("UCI HAR Dataset/activity_labels.txt", col.names = c("code", "activity")) subject_test <- read.table("UCI HAR Dataset/test/subject_test.txt", col.names = "subject") x_test <- read.table("UCI HAR Dataset/test/X_test.txt", col.names = features$functions) y_test <- read.table("UCI HAR Dataset/test/y_test.txt", col.names = "code") subject_train <- read.table("UCI HAR Dataset/train/subject_train.txt", col.names = "subject") x_train <- read.table("UCI HAR Dataset/train/X_train.txt", col.names = features$functions) y_train <- read.table("UCI HAR Dataset/train/y_train.txt", col.names = "code")

Setp-2: Merges the training and the test sets to create one data set.

X <- rbind(x_train, x_test) Y <- rbind(y_train, y_test) Subject <- rbind(subject_train, subject_test) Merged_Data <- cbind(Subject, Y, X)

Step-3: Extracts only the measurements on the mean and standard deviation for each measurement.

TidyData <- Merged_Data %>% select(subject, code, contains("mean"), contains("std"))

Step-4: Uses descriptive activity names to name the activities in the data set.

TidyData$code <- activities[TidyData$code, 2]

Step-5: Appropriately labels the data set with descriptive variable names.

names(TidyData)[2] = "activity" names(TidyData)<-gsub("Acc", "Accelerometer", names(TidyData)) names(TidyData)<-gsub("Gyro", "Gyroscope", names(TidyData)) names(TidyData)<-gsub("BodyBody", "Body", names(TidyData)) names(TidyData)<-gsub("Mag", "Magnitude", names(TidyData)) names(TidyData)<-gsub("^t", "Time", names(TidyData)) names(TidyData)<-gsub("^f", "Frequency", names(TidyData)) names(TidyData)<-gsub("tBody", "TimeBody", names(TidyData)) names(TidyData)<-gsub("-mean()", "Mean", names(TidyData), ignore.case = TRUE) names(TidyData)<-gsub("-std()", "STD", names(TidyData), ignore.case = TRUE) names(TidyData)<-gsub("-freq()", "Frequency", names(TidyData), ignore.case = TRUE) names(TidyData)<-gsub("angle", "Angle", names(TidyData)) names(TidyData)<-gsub("gravity", "Gravity", names(TidyData))

Step-6: From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

FinalData <- TidyData %>% group_by(subject, activity) %>% summarise_all(funs(mean)) write.table(FinalData, "FinalData.txt", row.name=FALSE)

-------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------
#### R code: run_analysis.R

## library(dplyr)
## setwd("/cloud/project")
## features <- read.table("UCI HAR Dataset/features.txt", col.names = c("n","functions"))
## activities <- read.table("UCI HAR Dataset/activity_labels.txt", col.names = c("code", "activity"))
## subject_test <- read.table("UCI HAR Dataset/test/subject_test.txt", col.names = "subject")
## x_test <- read.table("UCI HAR Dataset/test/X_test.txt", col.names = features$functions)
## y_test <- read.table("UCI HAR Dataset/test/y_test.txt", col.names = "code")
## subject_train <- read.table("UCI HAR Dataset/train/subject_train.txt", col.names = "subject")
## x_train <- read.table("UCI HAR Dataset/train/X_train.txt", col.names = features$functions)
## y_train <- read.table("UCI HAR Dataset/train/y_train.txt", col.names = "code")
## X <- rbind(x_train, x_test)
## Y <- rbind(y_train, y_test)
## Subject <- rbind(subject_train, subject_test)
## Merged_Data <- cbind(Subject, Y, X)
## TidyData <- Merged_Data %>% select(subject, code, contains("mean"), contains("std"))
## TidyData$code <- activities[TidyData$code, 2]
## names(TidyData)[2] = "activity"
## names(TidyData)<-gsub("Acc", "Accelerometer", names(TidyData))
## names(TidyData)<-gsub("Gyro", "Gyroscope", names(TidyData))
## names(TidyData)<-gsub("BodyBody", "Body", names(TidyData))
## names(TidyData)<-gsub("Mag", "Magnitude", names(TidyData))
## names(TidyData)<-gsub("^t", "Time", names(TidyData))
## names(TidyData)<-gsub("^f", "Frequency", names(TidyData))
## names(TidyData)<-gsub("tBody", "TimeBody", names(TidyData))
## names(TidyData)<-gsub("-mean()", "Mean", names(TidyData), ignore.case = TRUE)
## names(TidyData)<-gsub("-std()", "STD", names(TidyData), ignore.case = TRUE)
## names(TidyData)<-gsub("-freq()", "Frequency", names(TidyData), ignore.case = TRUE)
## names(TidyData)<-gsub("angle", "Angle", names(TidyData))
## names(TidyData)<-gsub("gravity", "Gravity", names(TidyData))
## FinalData <- TidyData %>%
  group_by(subject, activity) %>%
  summarise_all(funs(mean))
## write.table(FinalData, "FinalData.txt", row.name=FALSE)
## str(FinalData)
## FinalData
## End of R script
=============================================================================================================







