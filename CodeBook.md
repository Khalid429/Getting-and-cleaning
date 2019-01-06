Coursera Week4 Data Cleaning Project Solution
Khalid
January 2, 2019
Synopsis
This project stems from the Coursera Cleaning Data Course. It has 4 weeks of curriculum. In the 4th week, there is an assignment regarding data cleansing. This entire project is based upon the methodology of solving that assignment.
Project 
The objective here is to describe how a solution was drafted for the Coursera Cleaning Data Week 4 assignment. The issue is that many of times the code is rendered without the mindset behind the code. Here we are attempting to discuss both.
Assignment
Course is based upon the Coursera Cleaning Data Course Week 4 Assignment. R code was to have 5 immediate outcomes:
	1.	Merge training and test sets to create one data set
	2.	Extract only the mean and standard deviation measurements
	3.	Extract only the mean and standard deviation measurements
	4.	Label data set with descriptive variable names
	5.	From the outcome of 4, create an independent data set with average of each variable for each activity and subject
Data Set to be used
Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained:
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
Here are the data for the project:
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
Step by Step Method
Following are the main steps that are used to complete the requirements of the project:
Downloading and Cleaning the Data:
	•	A. Download the Data
	•	B. Since the data is in Zip format - unzip data
Downloading and Cleaning the Data
This is a prerequisite. You cannot move forward without getting the data downloaded and stored. In this particular case, the code also has to be unizipped.
For some odd reason the code is not allowing the URL to be placed here. Hence adding the main steps here
	•	A. Create a directory where the data is to be stored
	•	B. Create a URL named vector with the URL address
	•	C. Use the download.file function to download the file. Ensure that you use mode = wb - ensure binary data is received
	•	D. Use the unzip command and store the unzipped data into another directory
	•	E. Keep track of the path to use it for creating other vectors


##  [1] "activity_labels.txt"                         
##  [2] "features.txt"                                
##  [3] "features_info.txt"                           
##  [4] "README.txt"                                  
##  [5] "test/Inertial Signals/body_acc_x_test.txt"   
##  [6] "test/Inertial Signals/body_acc_y_test.txt"   
##  [7] "test/Inertial Signals/body_acc_z_test.txt"   
##  [8] "test/Inertial Signals/body_gyro_x_test.txt"  
##  [9] "test/Inertial Signals/body_gyro_y_test.txt"  
## [10] "test/Inertial Signals/body_gyro_z_test.txt"  
## [11] "test/Inertial Signals/total_acc_x_test.txt"  
## [12] "test/Inertial Signals/total_acc_y_test.txt"  
## [13] "test/Inertial Signals/total_acc_z_test.txt"  
## [14] "test/subject_test.txt"                       
## [15] "test/X_test.txt"                             
## [16] "test/y_test.txt"                             
## [17] "train/Inertial Signals/body_acc_x_train.txt" 
## [18] "train/Inertial Signals/body_acc_y_train.txt" 
## [19] "train/Inertial Signals/body_acc_z_train.txt" 
## [20] "train/Inertial Signals/body_gyro_x_train.txt"
## [21] "train/Inertial Signals/body_gyro_y_train.txt"
## [22] "train/Inertial Signals/body_gyro_z_train.txt"
## [23] "train/Inertial Signals/total_acc_x_train.txt"
## [24] "train/Inertial Signals/total_acc_y_train.txt"
## [25] "train/Inertial Signals/total_acc_z_train.txt"
## [26] "train/subject_train.txt"                     
## [27] "train/X_train.txt"                           
## [28] "train/y_train.txt"
At this stage the file are now unipped and there entire data set is ready to be evaluated. There are 28 files and that need to be analyzed. Refer above.
Note - This is the basis for the entire project. Ensure that this milestone is reached.
Data Analysis
In the data the readme.me document, you will get a detailed perspective of what to expect and how to manipulate the data. There are three core variables:
	1.	Main 2. Test 3. Train
Main : activity_labels Inertial Signals Inertial Signals Test: features subject_test subject_train Train: features.info X_test X_train
README y_test y_train ‘features_info.txt’: Shows information about the variables used on the feature vector. * - ‘features.txt’: List of all features. * - ‘activity_labels.txt’: Links the class labels with their activity name. * - ‘train/X_train.txt’: Training set. * - ‘train/y_train.txt’: Training labels. * - ‘test/X_test.txt’: Test set. *- ‘test/y_test.txt’: Test labels
Analysis shows that you can categorize the data into 4 segments * training set * test set * features * activity labels
Inertial Signal data is not required. Additionally, features and activity label are more for tagging and descriptive than data sets.
Making the Test and Training Set Data
The objective here is to make the test and training data as per the sequence stated above. 4 basic level data sets will be defined and created:
	1.	test data set
	2.	train data set
	3.	features data set
	4.	activity labels data set

Tagging the test and train data sets now - Objective 3 of the Assignment
The main objective was to merge the test and train data - Here are the R STEPS to ensure
Objective of the merger is now complete
2. Extracting only the measurements on the mean and standard deviation for each measurement
Here the understanding is to measure the mean and standard deviation values only. This can be possible through different means. Here we are using the grepl function to get the data and create a data set associated with the requirements.
3. Use descriptive activity names to name the activities in the data set
Label the data set with descriptive variable names
Do note that this was already previously done and now we are simply denoting the vectors that have the labels
setAllInOne and setForMeanAndStd are the outcomes and solutions
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
