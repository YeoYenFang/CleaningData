
# set working directory
> setwd (./coursera/UCI HAR Dataset)

# download the data
fileURL <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
download.file(fileURL, filename="W4project.zip", method="curl")

# load packages
Library(dplyr) # use in select columns
Library(data.table) # read table

# read in the data
activities <- read.table("activity_labels.txt", col.names = c("code", "activity")) # col.names label the data
features <- read.table("features.txt", col.names = c("sn","functions"))

subject_test <- readtable("test/subject_test.txt", col.names = "subject")
x_test <- read.table("test/X_test.txt", col.names = features$functions)
y_test <- read.table("test/y_test.txt", col.names = "code")

subject_train <- read.table("train/subject_train.txt", col.names = "subject")
x_train <- read.table("train/X_train.txt", col.names = features$functions)
y_train <- read.table("train/y_train.txt", col.names = "code")


# all subjects - Merge
allSubject <- rbind(subject_train, subject_test) # combine test and training subject 
allX <- rbind(x_train, x_test) # combine test and training records on measurement
allY <- rbind(y_train, y_test) # combine test and training records on activities
alldata <- cbind(allSubject, allY, allX) # combine all records and all data items

# extract variables for mean and standard deviation for each type of measurement
SelectedItem_Tidy <- select(alldata, code, contains("subjects"), contains("mean"), contains("std"))
# select is from dplyr package

# use activies description instead of code
SelectedItem_Tidy$code <- activities[SelectedItem_Tidy$code, 2]

# label the data items
names(SelectedItem_Tidy)[1] = "activity" 
names(SelectedItem_Tidy)<-gsub("Acc", "Accelerometer", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("Gyro", "Gyroscope", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("BodyBody", "Body", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("Mag", "Magnitude", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("^t", "Time", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("^f", "Frequency", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("tBody", "TimeBody", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("-mean()", "Mean", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("-std()", "STD", names(SelectedItem_Tidy))
names(SelectedItem_Tidy)<-gsub("-freq()", "Frequency", names(SelectedItem_Tidy))

# summary dataset
SummaryData <- SelectedItem_Tidy %>% 
  group_by(subject, activity) %>%
  summarise_all(funs(mean))
# "%>%" is from dplyr package

# output the data
write.table(SummaryData, file = "SummaryData.txt")
