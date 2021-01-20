# Getting and Cleaning Data
This repo is the submission for the **"Getting and Cleaning Data"** course project. The data set used for this project is available [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).
## Data set description
> This information has been taken from the site from where the data is obtained

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

## Files
-   `codebook.md` is a code book that describes the variables, the data, and any transformations or work that has been performed to clean the data.
-   `run_analysis.R` is the R script that performs the preparatory steps followed by the **5** steps as required in the project definition. The script performs the following actions correctly:
    1.   Merges the training and the test sets to create one data set.
    2.   Extracts only the measurements on the mean and standard deviation for each measurement.
    3.   Uses descriptive activity names to name the activities in the data set
    4.   Appropriately labels the data set with descriptive variable names.
    5.   From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
-   `Final.txt` is the final file containing the tidy data set after completion of all the steps.
