# CODE BOOK
This code book aims to summarize results and desscribe variables in FinalTidyData.txt after running run_analysis.R.
## 0. Download and create variables
* `features <- features.txt` : 561 rows, 2 columns. The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
* `activities <- activity_labels.txt` : 6 rows, 2 columns. List of activities performed when the corresponding measurements were taken and its codes (labels).
* `subject_test <- test/subject_test.txt` : 2947 rows, 1 column. It contains test data of 9/30 volunteer test subjects being observed.
* `x_test <- test/X_test.txt` : 2947 rows, 561 columns. It contains recorded features test data.
* `y_test <- test/y_test.txt` : 2947 rows, 1 columns. This variable contains test data of activities’code labels.
* `subject_train <- test/subject_train.txt` : 7352 rows, 1 column. It contains train data of 21/30 volunteer subjects being observed.
* `x_train <- test/X_train.txt` : 7352 rows, 561 columns. This variable comprises recorded features train data.
* `y_train <- test/y_train.txt` : 7352 rows, 1 columns. It composes train data of activities’code labels
## 1. Merges the training and the test sets to create one data set
* `X` (10299 rows, 561 columns) is created by merging `x_train` and `x_test` using `rbind()` function.
* `Y` (10299 rows, 1 column) is created by merging `y_train` and `y_test` using `rbind()` function.
* `Subject` (10299 rows, 1 column) is created by merging `subject_train` and `subject_test` using `rbind()` function.
* `Merged_Data` (10299 rows, 563 column) is created by merging `Subject`, `Y` and `X` using `cbind()` function.
## 2. Extracts only the measurements on the mean and standard deviation for each measurement
* `TidyData` (10299 rows, 88 columns) is created by subsetting `Merged_Data`, selecting only columns: `subject`, `code` and the measurements on the `mean` and standard deviation (`std`) for each measurement.
## 3. Uses descriptive activity names to name the activities in the data set
* Entire numbers in `code` column of the `TidyData` replaced with corresponding activity taken from second column of the `activities` variable
## 4. Appropriately labels the data set with descriptive variable names
* `code` column in `TidyData` renamed into `activities`.
* All `Acc` in column’s name replaced by `Accelerometer`.
* `tGravityAccStdY`
* `tGravityAccStdZ`
* `tBodyAccJerkMeanX`
* `tBodyAccJerkMeanY`
* `tBodyAccJerkMeanZ`
* `tBodyAccJerkStdX`
* `tBodyAccJerkStdY`
* `tBodyAccJerkStdZ`
* `tBodyGyroMeanX`
* `tBodyGyroMeanY`
* `tBodyGyroMeanZ`
* `tBodyGyroStdX`
* `tBodyGyroStdY`
* `tBodyGyroStdZ`
* `tBodyGyroJerkMeanX`
* `tBodyGyroJerkMeanY`
* `tBodyGyroJerkMeanZ`
* `tBodyGyroJerkStdX`
* `tBodyGyroJerkStdY`
* `tBodyGyroJerkStdZ`
* `tBodyAccMagMean`
* `tBodyAccMagStd`
* `tGravityAccMagMean`
* `tGravityAccMagStd`
* `tBodyAccJerkMagMean`
* `tBodyAccJerkMagStd`
* `tBodyGyroMagMean`
* `tBodyGyroMagStd`
* `tBodyGyroJerkMagMean`
* `tBodyGyroJerkMagStd`
* `fBodyAccMeanX`
* `fBodyAccMeanY`
* `fBodyAccMeanZ`
* `fBodyAccStdX`
* `fBodyAccStdY`
* `fBodyAccStdZ`
* `fBodyAccMeanFreqX`
* `fBodyAccMeanFreqY`
* `fBodyAccMeanFreqZ`
* `fBodyAccJerkMeanX`
* `fBodyAccJerkMeanY`
* `fBodyAccJerkMeanZ`
* `fBodyAccJerkStdX`
* `fBodyAccJerkStdY`
* `fBodyAccJerkStdZ`
* `fBodyAccJerkMeanFreqX`
* `fBodyAccJerkMeanFreqY`
* `fBodyAccJerkMeanFreqZ`
* `fBodyGyroMeanX`
* `fBodyGyroMeanY`
* `fBodyGyroMeanZ`
* `fBodyGyroStdX`
* `fBodyGyroStdY`
* `fBodyGyroStdZ`
* `fBodyGyroMeanFreqX`
* `fBodyGyroMeanFreqY`
* `fBodyGyroMeanFreqZ`
* `fBodyAccMagMean`
* `fBodyAccMagStd`
* `fBodyAccMagMeanFreq`
* `fBodyBodyAccJerkMagMean`
* `fBodyBodyAccJerkMagStd`
* `fBodyBodyAccJerkMagMeanFreq`
* `fBodyBodyGyroMagMean`
* `fBodyBodyGyroMagStd`
* `fBodyBodyGyroMagMeanFreq`
* `fBodyBodyGyroJerkMagMean`
* `fBodyBodyGyroJerkMagStd`
* `fBodyBodyGyroJerkMagMeanFreq`

## Activity Labels

* `WALKING` (value `1`): subject was walking during the test
* `WALKING_UPSTAIRS` (value `2`): subject was walking up a staircase during the test
* `WALKING_DOWNSTAIRS` (value `3`): subject was walking down a staircase during the test
* `SITTING` (value `4`): subject was sitting during the test
* `STANDING` (value `5`): subject was standing during the test
* `LAYING` (value `6`): subject was laying down during the test


