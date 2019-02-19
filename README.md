
** Explanation for the R code
1.	down load the data
2.	Load the required Packages  e.g. dplyr, data.table
3.	read.table into to R, assign the col.names 
4.	combine the data for test and training using rbind
5.	combine all the variables using cbind
6.	use select of dplyr to keep required variables and place in another data frame
7.	map the activity code to description and keep the description
8.	expand the abbreviation using gsub function
9.	compute mean by subject and activity, using summarize function with mean. Do this with dplyr package, and output to new data frame
10.	write the data frame from point 9 using write.table function

