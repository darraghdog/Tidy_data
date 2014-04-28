==================================================================
John Hopking "Getting and Claning Data" course assignment
Version 1.0
==================================================================
Darragh Hanley
https://www.coursera.org/
==================================================================

This assignment was carried out for the john Hopkins course assignments. The code carries out the following steps on data linked from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone.
A full description is available at the site where the data was obtained: 
	http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 
Here are the data for the project: 
	https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
======================================
Script Steps are seen below.


We use the following packages to execute the script.
	library(data.table)
	library(plyr)
	library(matrixStats)
	library(reshape2)


Step 1
 Downloads the zipped files from the provided URL
 Merges the training and the test sets to create one data set.
 The funtion lists the file names to ensure they are downloaded correctly
 The unzip function unzips the files and places them in the extrat directory specified (exidr) 
 Since LIST is set to false it will not output the file names which were unzipped, however it will overwrite the files each time they are extracted
 Read the files
 column bind the data frames,
 append the the two files into one data set
 renames the rows according to the features

Step 2
 Extracts only the measurements on the mean and standard deviation for each measurement. 
 calculate out the mean and SD for each measurement and place in a separate table

Step 3 & 4
 Uses descriptive activity names to name the activities in the data set
 Appropriately labels the data set with descriptive activity names. 
 add the activity labels to the full data set

Step 5
 In order to use dcast we must ensure the columns to cast are factors. Subject is currently a integer so first we must convert this.
 Assign the column names of full_set1 to a vector 
 For each of the two variables, label and subject, create a new tables with the average of each variable for each activity and each subject. 
 Assign a new column to each table with the indicator if the table is a subject or a label.
 Align the column names of the first two columns so both tables have the same column names and can be bound together
 bind the two columns together.

Step 6
 Output the tidy data table to a text file for later upload, and set the row names not to be outputted.

The outputted tidy data set has the following column names:
=========================================

1) variable - this indicates whether the row represents the average for a subject or label
2) value - this indicates the value for the subject or label for which we are calculating averages
3) The remainig columns represent each individual measurement for which we are taking averages.


The inputted dataset includes the following files:
=========================================

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

Notes: 
======
