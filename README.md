# School District Analysis
## Overview of the school district analysis
The school board notified that the original provided document, students_complete.csv, shows evidence of academic dishonesty. The reading and math grades for Thomas High School ninth-graders appear to have been altered. 

Therefore, the school board requested the following:
1. Replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact. 
2. Once the data is cleansed, repeat the school district analysis previously completed.
3. Write up a report describing how these changes affected the overall analysis.

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
[Image]

Cleansed Output:
[Image]

After cleansing the data by removing 461 math and reading scores belonging to 9th graders from Thomas High School, the output from the original district analysis barely change. The Overall Passing percentage dropped by one percent, but all other key metrics remained virtually the same. This is somewhat expected, considering that the original file has over 40,000 student data points, and we turned into null barely one percent of teh data set.

### How is the school summary affected?
Original Output:
[Image]

Cleansed Output:
[Image]

If we focused on the per school analysis,we can witness a greater impact from nulling the data, specifically on the subject passing rate. Math and Reading passing rates dropped approximately by 27 percent, with the Overall Passing rate dropping five percent. This is because in the adjusted analysis, we calculated a new student count, as seen in the image below, which in turn changed the denominator used in the rate calculations.

[count code]


### How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
Original Output:
[Image]

Clenased Output:
[Image]

Relative to other schools, we can see that Thomas High School performance ranking dropped from second to eight place.

### How does replacing the ninth-grade scores affect the following:
#### Math and reading scores by grade
Scores by school spending
Scores by school size
Scores by school type
Summary: Summarize four changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.
