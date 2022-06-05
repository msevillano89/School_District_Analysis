# School District Analysis
## Overview of the school district analysis
The school board notified that the original provided document, students_complete.csv, shows evidence of academic dishonesty. The reading and math grades for Thomas High School ninth-graders appear to have been altered. 

Therefore, the school board requested the following:
1. Replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact. 
2. Once the data is cleansed, repeat the school district analysis previously completed.
3. Write a report describing how these changes affected the overall analysis.

As a reminder, the original analysis required:
- A high-level snapshot of the district's key metrics, presented in a table format
- An overview of the key metrics for each school, presented in a table format
- Tables presenting each of the following metrics:
  - Top 5 and bottom 5 performing schools, based on the overall passing rate
  - The average math score received by students in each grade level at each school
  - The average reading score received by students in each grade level at each school
  - School performance based on the budget per student
  - School performance based on the school size 
  - School performance based on the type of school

## Results
Upon cleansing the data, we observe the following results:
### How is the district summary affected?
Original output:
![Original district summary](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_district_summary.png)

Cleansed Output:
![Cleansed district summary](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_district_summary.png)

After cleansing the data by removing 461 math and reading scores belonging to 9th graders from Thomas High School, the original district analysis's output barely changed. The Overall Passing percentage dropped by one percent, but all other key metrics remained virtually the same. The result is expected, considering that the original file has over 40,000 student data points, and we turned into null barely one percent of the data set.

### How is the school summary affected?
Original Output:
![Original school summary](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_THS_summary.png)

Cleansed Output:
![Cleansed school summary](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_THS_summary.png)

Focusing on the per school analysis can witness a more significant impact from nulling the data, specifically on the subject passing rate. Math and Reading passing rates dropped approximately 27 percent, with the Overall Passing rate dropping five percent. This drop is because we calculated a new student count in the adjusted analysis, as seen in the ImageImage below, which changed the denominator used in the rate calculations.
```
# Step 1. Get the number of students that are in ninth grade at Thomas High School.
# These students have no grades. 
student_no_grades_count = student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"),"student_name"].count()

# Get the total student count 
student_count = school_data_complete_df["Student ID"].count()

# Step 2. Subtract the number of students that are in ninth grade at 
# Thomas High School from the total student count to get the new total student count.
new_student_count = student_count - student_no_grades_count
```

### How does replacing the ninth graders' math and reading scores affect Thomas High School's performance relative to the other schools?
Original Output:
![THS original performance](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_THS_performance.png)

Cleansed Output:
![THS cleansed performance](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_THS_performance.png)

Relative to other schools, we can see that Thomas High School's performance ranking dropped from second to eighth place.

### How does replacing the ninth-grade scores affect the following:
#### Math and reading scores by grade
Because we only replaced the ninth graders' scores, we see a 'NaN' value in the summary data when running the analysis. The scores for tenth to twelfth graders remain unaffected. See image below:

Math Scores:

![THS Math Scores](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_THS_math.png)

Reading Scores:

![THS Reading Scores](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_THS_reading.png)

#### Scores by school spending
Original Output:
![Original school spending](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_Spending.png)

Cleansed Output:
![Cleansed school spending](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_Spending.png)

Thomas High School has a school spending range of **$631 - $645**. There is virtually no impact by nulling the ninth graders' scores.

### Scores by school size
Original Output:
![Original school size](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_size.png)

Cleansed Output:
![Cleansed school size](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_size.png)

Thomas High School falls in the **medium-sized range**. As noted in the images above, there is virtually no chance.

#### Scores by school type
Original Output:
![Original school type](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Original_type.png)

Cleansed Output:
![Cleansed school type](https://github.com/msevillano89/School_District_Analysis/blob/main/Resources/Cleansed_type.png)

Thomas High School is a **charter school**. As noted, there was minimal impact on the original analysis.

### Summary
Thomas High School's results are summarized as follows:
- The overall passing rate dropped from 91% to 65%.
- Data cleansing greatly impacted the passing score rates. Score averages remained virtually unchanged.
- Ranking dropped from 2nd to 8th in the district.
- Math and reading scores will now show as 'NaN' in reports for the 9th-grade students at a grade level.
