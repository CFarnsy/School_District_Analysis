# School District Analysis:

## Overview of School District Analysis:
The chief data scientist for the school board has asked for help analyzing information about the schools in the district.  They have provided standardized testing data for the students and schools and requested the following information:
1.	A table showing the top and bottom five performing schools based on the passing rate.
2.	The average math score received by students in each grade at each school.
3.	The average reading score received by students in each grade at each school.
4.	The school’s performance based on the budget per student.
5.	The school’s performance based on the school size.
6.	The school’s performance based on the type of school.

### Purpose of this analysis:
The purpose of the analysis is to provide a high-level snapshot of key metric information for each school in the district.  This information will help the school board make strategic decision regarding priorities and funding allocations for the school budgets.

### Data Clean-up:
In order to complete the analysis, a clean-up of the data files was completed.  The clean-up consisted of checking for missing values and fixing student names.  Additionally, the information was received in separate files and the analysis required it be merged together into several different DataFrames. 

## Updated Analysis Overview:
After reviewing the preliminary results of the analysis, the school board believes the data shows the reading and math scores for the ninth graders at Thomas High School appear to have been altered.  

The school board wants to uphold the state-testing standards and have requested the analysis be adjusted.  They have requested to have the scores for the ninth graders at Thomas High School removed from the analysis while keeping the rest of the data intact.  After the ninth-grade math and reading scores were replaced with NaNs.  The updated data analysis was performed on the cleaned data set and NaNs were excluded from the aggregate calculations. 

## Updated Analysis Results:

Note: This is code and results showing the math and reading scores for the ninth graders at Thomas High School being replaced with NaNs.
### Step 2. Select all the reading scores from the ninth grade at Thomas High School and replace them with NaN.
student_data_df.loc[(student_data_df["school_name"]=="Thomas High School")&(student_data_df["grade"]=="9th"),"reading_score"]=np.nan
student_data_df

###  Step 3. Refactor the code in Step 2 to replace the math scores with NaN.
student_data_df.loc[(student_data_df["school_name"]=="Thomas High School")&(student_data_df["grade"]=="9th"),"math_score"]=np.nan
student_data_df

### Results:
![Replace ninth grade scores with NaN](https://user-images.githubusercontent.com/99366022/159623436-6639d50c-5ce8-4f11-8ddd-6478973cc346.png)

### The next several images are the original and updated DataFrames showing the results of the reading and math scores of ninth graders at Thomas High School being removed from the calculations.

1.	A table showing the top five performing schools based on the passing rate - slight decrease in % Overall Passing from 90.948012 to 90.630324.

Ninth grade scores included:
![Top 5 Schools - Original](https://user-images.githubusercontent.com/99366022/159623507-6f6af92d-f93d-4905-9880-ef4770df28a6.png)

Ninth grade scores removed:
![Top 5 Schools - Updated](https://user-images.githubusercontent.com/99366022/159624127-b20c72c6-a562-4760-9c3e-7978c3372f46.png)

2.	A table showing the bottom five performing schools based on the passing rate - no change in the schools listed.

Ninth grade scores included:
![Bottom 5 Schools - Original](https://user-images.githubusercontent.com/99366022/159623539-92030fc6-e5cc-4b82-8495-d82e6a9337dc.png)

Ninth grade scores removed:
![Bottom 5 Schools - Updated](https://user-images.githubusercontent.com/99366022/159623544-32a525f8-ea53-4cd8-bfb4-027294575745.png)

3.	The average math score received by students in each grade at each school - NaN showing for ninth grade, no other changes.

Ninth grade scores included:

![Average Math Scores - Original](https://user-images.githubusercontent.com/99366022/159623589-3560b961-3c26-4eae-a8b9-9ba4a9f1c972.png)

Ninth grade scores removed:

![Average Math Scores - Updated](https://user-images.githubusercontent.com/99366022/159623607-dd0c492b-2646-4352-85d8-97cef6a97605.png)

4.	The average reading score received by students in each grade at each school - NaN showing for ninth grade, no other changes.

Ninth grade scores included:

![Average Reading Scores - Original](https://user-images.githubusercontent.com/99366022/159623647-c9023161-0dff-4250-a606-3bcd5a88494a.png)

Ninth grade scores removed:

![Average Reading Scores - Updated](https://user-images.githubusercontent.com/99366022/159623655-08f1c547-f0a0-4f95-ac7c-8bd4e3fbab01.png)

5.	The school’s performance based on the budget per student - in the 631 - 645 range there is a slight decrease in % Overall Passing from 62.857656 to 62.778233.

Ninth grade scores included:
![Spending Per Student - Original](https://user-images.githubusercontent.com/99366022/159623679-892bb643-4359-4bcf-a43c-3caa660a4f24.png)

Ninth grade scores removed:
![Spending Per Student - Updated](https://user-images.githubusercontent.com/99366022/159623684-2262dbf8-9a69-4b22-9de4-5b730b64afe3.png)

6.	The school’s performance based on the school size - in the Medium range there is a slight decrease in % Overall Passing from 90.621535 to 90.557997.

Ninth grade scores included:
![Spending Per School Size - Original](https://user-images.githubusercontent.com/99366022/159623773-a5554387-44dd-474f-a2be-643f1e4397d9.png)

Ninth grade scores removed:
![Spending Per School Size - Updated](https://user-images.githubusercontent.com/99366022/159623812-f84ff093-adbb-42a0-8abb-5c904f9c736f.png)

7.	The school’s performance based on the type of school - in Charter schools there is a slight decrease in % Overall Passing from 90.432244 to 90.392533.

Ninth grade scores included:

![Spending Per School Type - Original](https://user-images.githubusercontent.com/99366022/159623830-77908dd5-51e4-4eda-8570-ed41ce2b108e.png)

Ninth grade scores removed:

![Spending Per School Type - Updated](https://user-images.githubusercontent.com/99366022/159623840-2ee55961-7f73-49ea-936e-7388488915f3.png)

## School District Analysis Updated Summary:
There were 461 ninth grade students reading and math scores at Thomas High School removed from the updated calculations.  However, there was a miniscule impact to the calculations based on comparing the results before and after the scores were removed.

As you can see in the images above as well as the images below there was very little, if any, impact to removing the scores.

-	How is the district summary affected?
The % Overall Passing total decreased slightly from 65.172326 to 64.855718

Ninth grade scores included:
![District Totals - Original](https://user-images.githubusercontent.com/99366022/159623866-44ac1817-2cf8-4021-b7ae-1749388f59bb.png)

Ninth grade scores removed:
![District Totals - Updated](https://user-images.githubusercontent.com/99366022/159623881-998d5140-2a54-4807-9e1e-e151be74e532.png)

-	How is the school summary affected?
The % Overall Passing total decreased slightly from 90.948012 to 90.630324.

Ninth grade scores included:
![School Summary - Original](https://user-images.githubusercontent.com/99366022/159623902-2da9efc7-44fc-4a95-bc68-274bca986c7b.png)

Ninth grade scores removed:
![School Summary - Updated](https://user-images.githubusercontent.com/99366022/159623917-751c0dd6-482e-47fa-9560-7f9a8a375453.png)

-	How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
Thomas High School was in ranked second in top five schools before and after the scores were removed.  Please see top five performing schools based on the passing rate shown above.)

-	How does replacing the ninth-grade scores affect the following:
The math and reading scores by grade, scores by school spending, scores by school size, and scores by school type changed less than .5 after the ninth-grade scores were removed from the original numbers. (Please see images above for additional details.)
