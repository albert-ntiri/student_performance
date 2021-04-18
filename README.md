# Student Performance - Factors That Affect Scores in Math, Reading, and Writing

## Overview
In this project, I take a look at the impact different factors have on students' math, reading, and writing scores.  The data set does not contain any personally identifiable information.  It is not real data.  It just has general information about a set of students, in a generalized way.  In addition to analyzing the data, I use machine learning to predict student scores based on the data set.

## Files
- [Student_Performance_EDA.ipynb](https://github.com/albert-ntiri/student_performance/blob/main/Student_Performance_EDA.ipynb): This notebook contains the initial exploration of the data using descriptive statistics.
- [Student_Performance_Feature_Engineering.ipynb](https://github.com/albert-ntiri/student_performance/blob/main/Student_Performance_Feature_Engineering.ipynb): This notebook contains the creation of group statistics to add to the original data set using object-oriented programming.
- [Student_Performance_Models.ipynb](https://github.com/albert-ntiri/student_performance/blob/main/Student_Performance_Models.ipynb): This notebook contains the predictive models where I attempt to predict student performance.

## Data Summary
The data set consists of 1,000 rows, each representing a student, and 8 columns.  Here are the columns in this data set:
- **gender**: whether the student is listed as male or female
- **race/ethnicity**: one of five generalized races listed for the student (group A - group E)
- **parental level of education**: the highest level of education the student's parents attained, ranging from some high school to master's degree
- **lunch**: whether the student is on free/reduced lunch
- **test preparation course**: whether the student has completed a test preparation course
- **math score**: the numerical score for the math section of the test, on a 0-100 scale
- **reading score**: the numerical score for the reading section of the test, on a 0-100 scale
- **writing score**: the numerical score for the writing section of the test, on a 0-100 scale

This data set did not require any cleaning.  There are no missing values or duplicate rows.  A box and whisker plot shows some outliers on the low end of the scores for all 3 subjects, but since they are still in the 0-100 range and that is a reasonable outcome in some cases, I did not remove them.

Most of the students in this data set are not on free/reduced lunch and did not take a test preparation course.  There are slightly more females than males and the most common races are group C and group D, with group A being the least common.  The parental level of education is fairly evenly distributed with no level representing more than 25% of the students and the most highly educated being the least common.  This group of students performed slighly lower on math than in reading and writing on average.  Reading and writing scores were highly correlated.  On average, males had high math scores while females had higher reading and writing scores.  All of the other categorical variables were consistent across subjects on which groups had the highest scores: group E for race, higher parental level of education, not free/reduced lunch, and having taken a test preparation course.

## Process
1. The first step in this analysis was to do descriptive statistics to understand each of the variables in the data set.  Once I had a solid understanding of the data, I looked at correlations between each variable and the scores to gain a high-level understanding of their impact.
2. The second step was to generate a set of group statistics to determine if they add any additional information and/or contribute to a student's performance.
3. The third step was to run a regression on the variables provided, as well as group statistics I generated, to determine how well they predict a student's performance.

## Insights
There are a few takeaways from the regression model:
1. The largest determinant of student performance in a particular subject is student performance in other subjects.
2. Individual student information (gender, race/ethnicity, lunch, parental level of education, test preparation course) have the same aggregate impact as the combination of group statistics.  Once one of them is there, the impact of adding the other is miniscule.
3. The impact of gender is different across subjects.  It is the only one of the individual variables that has a different impact, depending on the subject.
