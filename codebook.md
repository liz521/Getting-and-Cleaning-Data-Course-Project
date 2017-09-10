# Merges the training and the test sets to create one data set
## 1.Original Data Set

- 'features_info.txt': Shows information about the variables used on the feature vector.

- 'features.txt': List of all features.

- 'activity_labels.txt': Links the class labels with their activity name.

- 'train/X_train.txt': Training set.

- 'train/y_train.txt': Training labels.

- 'test/X_test.txt': Test set.

- 'test/y_test.txt': Test labels.

The following files are available for the train and test data. Their descriptions are equivalent. 

- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

- 'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. 

- 'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration. 

- 'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. 

## 2.Load data into R
- train.x: read from X_train.txt
- train.y: read from y_train.txt
- train.subject: read from subject_train.txt
- test.x: read from X_test.txt
- test.y: read from y_test.txt
- test.subject: read from subject_test.txt

## 3.Merge data
- trainData: column bind by train.y and train.x
- testData: column bind by test.y and test.x
- fullData: row bind by trainData and testData

# extract mean and standard deviation
use grep to extract mean and standard deviation
variable:
subject: name the subject
activity: name the activity

#Uses descriptive activity names to name the activities

#Appropriately labels the data set
names(finalData) <- gsub("\\()", "", names(finalData))
names(finalData) <- gsub("^t", "time", names(finalData))
names(finalData) <- gsub("^f", "frequence", names(finalData))
names(finalData) <- gsub("-mean", "Mean", names(finalData))
names(finalData) <- gsub("-std", "Std", names(finalData))

#Final output:tidyData.txt
180 obs. of  68 variables
