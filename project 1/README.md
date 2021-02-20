# general-assembly-projects

# **Project 1: SAT & ACT Analysis**

Here we explore the 2017 and 2018 SAT & ACT data sets for each US State, studying the participation rates, score breakdown by individual subjects, total scores for SATs and composite scores for the ACT. Our goal is to increase participation rates for either of these 2 tests, and to study the correlation between participation rates and test scores for each state.

## **Problem Statement**

With declining SAT participation rates due to the ACT seizing a greater market share, greater emphasis must be placed on restoring the College Board's status with its redesigned SAT. This project aims to identify opportunities for the College Board to increase the SAT participation rates across US states via ab in-depth analysis of the 2017 and 2018 SAT and ACT data sets. The goal is to determine which states should be targeted to raise the current SAT participation rates.


## **Data Dictionary**

|Feature|Type|Dataset|Description
|:-|:---:|:---:|:-|
|**state**|object|sat_df|2017 SAT state data|
|**sat_part_2017**|float|sat_df|Participation rate for SAT by state in 2017 (units percent to two decimal places 0.98 means 98%)|
|**sat_read_2017**|float|sat_df|State-wide mean score for SAT Evidence-Based Reading and Writing tests in 2017|
|**sat_math_2017**|float|sat_df|State-wide mean score for SAT Math tests in 2017|
|**sat_total_2017**|float|sat_df|State-wide mean total score for SAT in 2017|
|**act_part_2017**|float|act_df|Participation rate for ACT by state in 2017 (units percent to two decimal places 0.98 means 98%)|
|**act_eng_2017**|float|act_df|State-wide mean score for ACT English tests in 2017|
|**act_math_2017**|float|act_df|State-wide mean score for ACT Math tests in 2017|
|**act_read_2017**|float|act_df|State-wide mean score for ACT Reading tests in 2017|
|**act_sci_2017**|float|act_df|State-wide mean score for ACT Science tests in 2017|
|**act_comp_2017**|float|act_df|State-wide mean composite score for ACT in 2017|
|**sat_part_2018**|float|sat_df|Participation rate for SAT by state in 2018 (units percent to two decimal places 0.98 means 98%)|
|**sat_read_2018**|float|sat_df|State-wide mean score for SAT Evidence-Based Reading and Writing tests in 2018|
|**sat_math_2018**|float|sat_df|State-wide mean score for SAT Math tests in 2018|
|**sat_total_2018**|float|sat_df|State-wide mean total score for SAT in 2018|
|**act_part_2018**|float|act_df|Participation rate for ACT by state in 2018 (units percent to two decimal places 0.98 means 98%)|
|**act_eng_2018**|float|act_df|State-wide mean score for ACT English tests in 2018|
|**act_math_2018**|float|act_df|State-wide mean score for ACT Math tests in 2018|
|**act_read_2018**|float|act_df|State-wide mean score for ACT Reading tests in 2018|
|**act_sci_2018**|float|act_df|State-wide mean score for ACT Science tests in 2018|
|**act_comp_2018**|float|act_df|State-wide mean composite score for ACT in 2018|
