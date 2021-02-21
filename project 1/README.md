# **Project 1: SAT & ACT Analysis**

## **Problem Statement**

With declining SAT participation rates statewide due to the seemingly unstoppable ACT seizing increasing market share, greater emphasis must be placed on restoring the College Board's premier status with its redesigned SAT. 

By conducting thorough analyses on the datasets containing the average SAT and ACT scores by state, as well as participation rates for the graduating class of 2017/18, key insights have been identified to aid us in providing recommendations to the College Board to boost SAT participation rates in a suitable state.

## **Executive Summary**

This exploratory data analysis combines the use of a heatmap, histograms, scatter plots and boxplots to obtain a complete statistical picture of the data sets. The findings show that high participation rates for a test in one state usually corresponds with low participation rates in the other test, particularly for states where one of the tests is mandatory. We also see that fluctuations in participation rates from 2017 to 2018 were a consequence of state education laws switching preferences between the SAT and ACT, or completely doing away with standardised testing. As such, we recommend reducing efforts to increase participation rates in states that have either recently begun mandatory ACT testing, or removed the need for such tests. 

The list of suitable states was narrowed down by eliminating states which already require standardised testing, as well as states that offer financial subsidies for these tests. Another layer of filtering was applied to reveal which states had less than 50% participation rates in both of these tests. Two states were initially identified (Alaska and Oregon) and with further analysis, the final recommendation is for the College Board to focus its efforts on increasing SAT participation rates in the state of Oregon. 

We do advise providing sufficient time for states to transition over to mandatory state testing, as large increases in participation rates are negatively correlated with test scores, mainly due to the need for schools and institutions to roll out large-scale changes to accommodate the SAT syllabus and assessment criteria.

This report also investigates the limitations of performing statistical inferences that rely on the characteristics of a normal distribution or the Central Limit Theorem. As mentioned above, constant changes in state laws result in fluctuating participation rates. In addition, some students may sit for both the SAT and ACT, resulting in self-selection bias which may not be revealed obviously but can skew the results in a large way.  

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


## **Conclusions and Recommendations**

#### **Key Takeaways**

The analysis conducted above has revealed the following insights: 
- High participation rates in either test usually indicate low participation rates in the other test
- There is a relatively strong negative correlation between high participation rates and mean test scores, ranging between a coefficient of -0.79 to -0.87
- There is a strong positive correlation between 2017/2018 SAT total scores and ACT composite scores, ranging between a coefficient of 0.85 to 0.94. 
- Fluctuations in participation rates were a result of changing education laws. 
- A sufficiently long time period must be given to states to transition over to mandatory testing as large increases in participation rates are negatively correlated with test scores. 
- Limitations of statistical inferences relying on the characteristics of a normal distribution or the Central Limit Theorem were noted. Constant changes in state laws result in fluctuating participation rates. In addition, some students may sit for both the SAT and ACT, resulting in self-selection bias which may not be revealed obviously but can skew the results in a large way.  


#### **Recommendations**

In our above considerations for states which neither require standardised testing nor offer financial support to test-takers, Oregon is an optimal choice for the College Board to focus its efforts on to boost its participation rates, since Alaska no longer remains a viable option. With a 48% SAT participation rate, Oregon is close to tipping over the 50% mark which may be viewed as a psychological level of resistance, since students tend to be heavily influenced by their peers. 

It is recommended that the College Board engages in collaborations with the Oregon Department of Education and local education agencies to set up statewide SAT testing requirements, offer full or partial coverage of exam fees and consider the possibility of offering scholarships to test-takers with exemplary scores. We would caution against offering free test preparation programs for students as studies have revealed that this has a negative impact on students, due to the social stigma associated with taking up free education activities, specifically for those of a lower socioeconomic status. However, the College Board may consider subsidising such programs (as opposed to fully funding them) or engaging with schools to increase their efforts to help students with their SAT preparations. 

#### **Additional Useful Data**

Further data that may benefit our analysis would include:
- SAT participation rates and test scores by cities and schools. 
- Socioeconomic indicators such as average household incomes of test-takers and race 
