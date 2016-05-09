getting_and_cleaning_data
=========================

As part of the Specialization Program @ John's Hopkins Bloomberg School of Public Health

TO-DO List:

A. Merge the training and the test sets to create one data set.
B. Extract only the measurements on the mean and standard deviation for each measurement. 
C. Use descriptive activity names to name the activities in the data set
D. Appropriately label the data set with descriptive activity names. 
E. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 


A. Merge the training and the test sets to create one data set.

Steps:
- Set working directory to the location where the UCI HAR Dataset was unzipped
- Read in the data from files
- Assigin column names to the data imported above
- Create the final training set by merging yTrain, subjectTrain, and xTrain
- Read in the test data
- Assign column names to the test data imported above
- Create the final test set by merging the xTest, yTest and subjectTest data
- Combine training and test data to create a final data set
- Create a vector for the column names from the finalData, which will be used to select the desired mean() & stddev() columns


B. Extract only the measurements on the mean and standard deviation for each measurement. 

Steps:
- Create a logicalVector that contains TRUE values for the ID, mean() & stddev() columns and FALSE for others
- Subset finalData table based on the logicalVector to keep only desired columns


C. Use descriptive activity names to name the activities in the data set

Steps:
- Merge the finalData set with the acitivityType table to include descriptive activity names
- Updating the colNames vector to include the new column names after merge


D. Appropriately label the data set with descriptive activity names. 

Steps:
- Cleaning up the variable names
- Reassigning the new descriptive column names to the finalData set


E. Create a second, independent tidy data set with the average of each variable for each activity and each subject. 

Steps:
- Create a new table, finalDataNoActivityType without the activityType column
- Summarizing the finalDataNoActivityType table to include just the mean of each variable for each activity and each subject
- Merging the tidyData with activityType to include descriptive acitvity names
- Export the tidyData set
