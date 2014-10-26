# Getting and Cleaning Data Course Project

## Project requirements

The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. 
The goal is to prepare tidy data that can be used for later analysis. 
You will be graded by your peers on a series of yes/no questions related to the project. 
You will be required to submit: 1) a tidy data set as described below, 
2) a link to a Github repository with your script for performing the analysis, and 
3) a code book that describes the variables, the data, and any transformations or 
work that you performed to clean up the data called CodeBook.md. 
You should also include a README.md in the repo with your scripts. 
This repo explains how all of the scripts work and how they are connected.  

One of the most exciting areas in all of data science right now is wearable computing - 
see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to 
develop the most advanced algorithms to attract new users. The data linked to from the course 
website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. 
A full description is available at the site where the data was obtained: 

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

Here are the data for the project: 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 

 
You should create one R script called run_analysis.R that does the following. 

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the 
average of each variable for each activity and each subject.

## Logic of function run_analysis()
### Assumption
The archives containing the data have been downloaded and unzipped. 
The root folder has been renamed from "UCI HAR Dataset" to "GCD" (Getting and Cleaning Data).
The data files are located in "E:/datascience"

### Logic
The function reads the data values, the subject id values, and the activity id values from the appropriate
files for both the training and testing data sets.

The function reads the features file which contains the names of the variables (column header names)

The function changes the column header names to make them more readable.

The activity labels are read into a vector as we want to replace activity ids with a descriptive name.

The altered column names are added to the training and test data sets.

The data sets are filtered for variables that have 'Mean' and 'Std' in their names.

The subject ids are added to the data sets.

Activity ids on both data sets are replaced with activity names

The training and testing data sets are merged

A new data set is created through the aggregate function to accomplish requirement number five above.

This new data set is written out to a file. 

