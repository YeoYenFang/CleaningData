
## The experiment is
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain. See 'features_info.txt' for more details. 

## Data files
•	activity_labels.txt: contains the label for activities tested
•	features.txt: contains the labels for all measured features
•	subject_test.txt: Subject number
•	X_test.txt: contains test subjects’ measured features
•	y_test.txt: contains: test subjects’ activities measured
•	subject_train.txt: contains
•	X_train.txt: contains train subjects’ measured features
•	y_train.txt: contains train subjects’ activities measured

## Variables
•	tBodyAcc-XYZ: Time Body Acceleration 
•	tGravityAcc-XYZ: Time Gravity Acceleration 
•	tBodyAccJerk-XYZ: Time Body Acceleration Jerk 
•	tBodyGyro-XYZ: Time Body gyroscope 
•	tBodyGyroJerk-XYZ: Time Body gyroscope Jerk
•	tBodyAccMag: Time Body Acceleration magnitude
•	tGravityAccMag: Time Gravity Acceleration magnitude
•	tBodyAccJerkMag: Time Body Acceleration Jerk magnitude
•	tBodyGyroMag: Time Body gyroscope magnitude
•	tBodyGyroJerkMag: Time Body gyroscope Jerk magnitude
•	fBodyAcc-XYZ: Frequency Body Acceleration
•	fBodyAccJerk-XYZ: Frequency Body Acceleration
•	fBodyGyro-XYZ: Frequency Body gyroscope
•	fBodyAccMag: Frequency body Acceleration magnitude
•	fBodyAccJerkMag: Frequency body Acceleration Jerk magnitude
•	fBodyGyroMag: Frequency body gyroscope magnitude
•	fBodyGyroJerkMag: Frequency body gyroscope Jerk magnitude

mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.

Activities
1 WALKING
2 WALKING_UPSTAIRS
3 WALKING_DOWNSTAIRS
4 SITTING
5 STANDING
6 LAYING

## License:
===========
Use of this dataset in publications must be acknowledged by referencing the following publication [1] 

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

This dataset is distributed AS-IS and no responsibility implied or explicit can be addressed to the authors or their institutions for its use or misuse. Any commercial use is prohibited.

Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita. November 2012.
