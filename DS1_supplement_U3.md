<style scoped> @import url("rmd_doc_suffix.css"); </style>
# DS1 Course Supplemental Resources


## Unit 3: Data Wrangling

Sometimes students have find the video online Data Camp exercises difficult to work with. 

When watching the videos on dplyr manipulation, open RStudio, download the related files (i.e. for the "hands-on dplyr tutorial"), and work some of the problems. Gain some practice in the real environment, and don't just watch.

The links below cover the same lessons in a different format, and I offer them for students who are looking for an alternative to the Data Camp material.

### Tidy data

When we talk about *data wrangling*, we mean the process of reorganizing data to make it easier to analyze. Often we find data in formats that were designed to be human-readable, or perhaps easy for data-entry, but not for data analysis. In these cases, we need to transform the structure of the data.

[Section 12.2](http://r4ds.had.co.nz/tidy-data.html#tidy-data-1) of Hadley Wickham's *R for Data Science* offers some examples of different data formats, and talks about the advantage of *tidy data* for data analysis. Read that section and complete the exercises in 12.2.1. You do not need to read the rest of that chapter right away.

### Core resources for data wrangling

Chapter 5, [Data transformation](http://r4ds.had.co.nz/transform.html), of *R for Data Science* covers much of the same material as unit 3.1 in Springboard's *Foundations of Data Science* course. Read that chapter and complete the exercises.

Then finish chapter 12, "[Tidy data](http://r4ds.had.co.nz/tidy-data.html#spreading-and-gathering)," and complete the exercises.

You should now be able to complete the three Springboard mini-projects found in unit 3.1, "Core Resources for Data Wrangling:" "Data Wrangling Exercise 1: Basic Data Manipulation," "Data Wrangling Exercise 2: Dealing with missing values," and the option mini-project, "Data Wrangling Exercise 3: Human Activity Recognition."

## Additional practice

If the three mini-projects leave you wanting a little more practice, give this a try: [A Dirty Dataset for You to Clean](https://github.com/RMHogervorst/unicorns_on_unicycles) (thanks to [Roel Hogervorst](http://rmhogervorst.nl/cleancode/blog/2018/03/12/content/post/2018-03-12-a-dirty-dataset-for-you-to-clean/).

1. Download the two Excel (.xlsx) files.
2. Read the three tables from those files into three data frames, using the *readxl* package.
3. Join the data frames together, cleaning any mismatched data, using *dplyr*.
4. Create one long, tidy data frame with variables *country*, *year*, *value1*, *value2*, and *value3*.
5. Take only a few minutes to assess any missing values and try to categorize them as Missing Completely At Random (MCAR), Missing At Random (MAR), or Not Missing At Random (NMAR). Decide whether it is feasible to ignore the missing values, impute them, or omit them.

## Making sense of the Human Activity exercise

The instructions for the project are:

0. Load the data in RStudio  
 Load the training and test data sets into RStudio, each in their own data frame.

1. Merge data sets  
 Merge the training and the test sets to create one data set.

2. Mean and standard deviation  
 Create two new columns, containing the mean and standard deviation for each measurement respectively. Hint: Since some feature/column names are repeated, you may need to use the make.names() function in R.

3. Add new variables  
 Create variables called ActivityLabel and ActivityName that label all observations with the corresponding activity labels and names respectively

4. Create tidy data set  
 From the data set in step 3, creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

Most of the challenge in this exercise is working through steps 1 and 2. Getting the data, the activity names, the subject IDs, and the column labels, and merging them all into one coherent data frame, is a pretty big effort.

The confusion usually comes in steps 3 and 4.

Step 3 and 4 should read something like:

> Subset the data frame from step 2 so that you have the subject ID, Activity Name, and all of the mean and standard deviation columns, but nothing else.

> Then group and summarize the means and standard deviations for each activity across subjects, and create a summary data frame.




