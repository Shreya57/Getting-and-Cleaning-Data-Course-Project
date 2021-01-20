# Code Book
The `run_analysis.R` script performs the preparatory steps followed by the 5 steps as required in the project definition.
1. **Downloading the dataset**: Dataset downloaded and extracted under the folder "UCI HAR Dataset".
2. **Assign data to variables**:
   - features <- `features.txt`: (561 rows, 2 columns) The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
   - activities <- `activity_labels.txt`: (6 rows, 2 columns) List of activities performed when the corresponding measurements were taken and its codes (labels).
   - subject_test <- `test/subject_test.txt`: (2947 rows, 1 column) Contains test data of 9/30 volunteer test subjects being observed.
   - x_test <- `test/X_test.txt`: (2947 rows, 561 columns) Contains recorded features test data.
   - y_test <- `test/y_test.txt`: (2947 rows, 1 columns) Contains test data of activities’ code labels.
   - subject_train <- `test/subject_train.txt`: (7352 rows, 1 column)       Contains train data of 21/30 volunteer subjects being observed.
   - x_train <- `test/X_train.txt`: (7352 rows, 561 columns)       Contains recorded features train data
   - y_train <- `test/y_train.txt`: (7352 rows, 1 columns) Contains train data of activities’ code labels.
3. **Merge training and test sets to create one data set**:
   - x (10299 rows, 561 columns) created by merging "x_train" and "x_test" using rbind() function.
   - y (10299 rows, 1 column) created by merging "y_train" and "y_test" using rbind()  function.
   - subject (10299 rows, 1 column) created by merging "subject_train" and "subject_test" using rbind() function.
   - merged (10299 rows, 563 column) created by merging "subject", "y"  and "x" using cbind() function.
4. **Extract only the measurements on the mean and standard deviation for each measurement**: tidydata (10299 rows, 88 columns) created by subsetting "merged", selecting only columns: "subject", "code" and the measurements on the mean and standard deviation for each measurement.
5. **Use descriptive activity names to name the activities in the data set**: Entire numbers in "code" column of "tidydata" replaced with corresponding activity taken from second column of the "activities" variable.
6. **Label the data set appropriately with descriptive variable names**:
   - "code" in "tidydata" renamed to "activities"
   -  All "Acc" in column names changed to "Accelerometer"
   -  All "Gyro" in column names changed to "Gyroscope"
   -  All "BodyBody" in column names changed to "Body"
   -  All "Mag" in column names changed to "Magnitude"
   -  All columns starting with "f" changed to "Frequency"
   -  All columns starting with "t" changed to "Time"
7. **From "tidydata", created a second, independent tidy data set with the average of each variable for each activity and each subject**:
   - final (180 rows, 88 columns) created by summarizing "tidydata" by taking the means of each variable for each activity and each subject, after grouping by "subject" and "activity".
   -  Exported "final" to `Final.txt`.
