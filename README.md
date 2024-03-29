
# Data Cleaning and Organization Summary
Objective:
The provided Python script loads a CSV file containing diabetes prediction data, cleans and organizes the data, and performs initial exploratory data analysis.

1. Load the diabetes prediction dataset and rename columns.

2. Check for null values and explore the distribution of values in each column.

3. Standardize values in the Smoking History column.

4. Create quartiles for the Age column to divide the data into four equal parts.
   
5. Print quartile cutoffs to understand the age ranges for each quartile.

These steps aim to organize and prepare the dataset for analysis and potential machine learning tasks.

# Visualization of Raw Data Prior to Processing/Analysis

1.Box Plots:

      a) Compares age, BMI, HbA1c percentage, and blood glucose level between diabetics and non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/92b37e17-d962-41b6-99d5-cce1ec401903)

2.Bar Charts:

    a) Shows the counts of hypertension, heart disease, gender distribution, and smoking history among diabetics and non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/ae5d2d65-c720-48cb-ba21-08d9c3f6d3d1)

3.Data Aggregation:

    a) Counts occurrences of gender and smoking history combinations for each diabetes status.
    b) Groups data by diabetes status and calculates hypertension and heart disease counts.
    c) Renames columns for clarity in the grouped data.
    d) Displays DataFrame of counts for easier manipulation later on.

These visualizations and aggregations help understand the dataset before further analysis or modeling for diabetes prediction.

# Visualization of Correlation Matrices to Guide Hypothesis Testing
1.Correlation Matrix without Smoking History:

    a) Smoking history is removed due to its categorical nature, making it incompatible with correlation analysis.
    b) Gender is mapped to numeric values (label encoding).
    c) The correlation matrix is calculated and visualized using a heatmap to explore relationships among numerical variables.
    d) Correlation coefficients are annotated for easier interpretation.

![output](https://github.com/10H-K/diabetes/assets/152930492/622b4bc0-6488-4f63-a581-9b3501570980)

2.Explanation for Deletion of Smoking History:

    a) Another correlation matrix is created with smoking history included.
    b) Rows with "N/A" smoking history are removed to prevent distortion of correlation results.
    c) Both gender and smoking history are label encoded before computing the correlation matrix.
    d) The heatmap shows the correlation matrix with smoking history included.
    e) Deletion of rows with "N/A" smoking history removes significant data, which distorts the correlation analysis.

![output](https://github.com/10H-K/diabetes/assets/152930492/e454e925-4df3-4013-ad0a-cfc4752bbb18)

These visualizations serve to guide hypothesis testing and provide insights into potential relationships between variables in the diabetes dataset.

# Is the likelihood of having either hypertension, heart disease, or both conditions significantly higher for diabetics compared to non-diabetics?
Hypothesis Testing:

    a) Null Hypothesis (H0): Likelihood of hypertension, heart disease, or both is equal for diabetics and non-diabetics.
    b) Alternative Hypothesis (H1): Likelihood of hypertension, heart disease, or both is significantly higher for diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/9c8d4569-7968-445b-8a37-ada9ad22c095)

Z-Test of Proportions:

    a) Tested proportions for each condition category between diabetics and non-diabetics.
    b) Resulted in significant differences, suggesting an association between diabetes and hypertension/heart disease.

Percentages Visualization:

    a) Shows percentages of individuals with each condition category for diabetics and non-diabetics.
    b) Helps visualize the distribution differences between diabetics and non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/2add401f-01a7-4c92-a0f7-b2ff9d1def22)

Conclusion:
    
    The investigation found that diabetics have a notably higher chance of developing hypertension, heart disease, or both compared to non-diabetics.

# Is average Body Mass Index (BMI) significantly higher for individuals with diabetes?
Hypothesis Testing:

    a) Null Hypothesis (H0): No significant difference exists in average BMI levels between individuals with and without diabetes, regardless of age.
    b) Alternative Hypothesis (H1): Average BMI levels are significantly higher for individuals with diabetes compared to those without diabetes, irrespective of age.

![output](https://github.com/10H-K/diabetes/assets/152930492/a1dfc338-3d1a-4219-9d95-d1cccec031e6)

Mann-Whitney U Test:

    a) Utilized Mann-Whitney U test to compare average BMI levels between diabetics and non-diabetics across different age quartiles.
    b) Significant p-values support the alternative hypothesis, indicating higher BMI levels among individuals with diabetes, regardless of age.

Average BMI Visualization:

    a) Shows average BMI per age quartile for diabetics and non-diabetics.
    b) Helps visualize the differences in average BMI between diabetics and non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/fdff0650-0e79-4698-9fb9-4782068cfb3b)

Conclusion:
    
    The investigation found that individuals with diabetes have notably higher average BMI levels compared to those without diabetes. 

# Is the likelihood of having either a current or former history with smoking significantly higher for diabetics compared to non-diabetics?
Hypothesis Testing:

    a) Null Hypothesis (H0): The likelihood of having either a current or former history with smoking is the same for both diabetics and non-diabetics.
    b) Alternative Hypothesis (H1): The likelihood of having either a current or former history with smoking is significantly higher for diabetics compared to non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/c787a8a9-e1f4-42b9-897e-ecbc7021c94a)

Analysis Steps:

    a) Data Extraction: Obtained counts of current, former, and never smokers for both diabetics and non-diabetics.
    b) Contingency Table: Created a contingency table to compare smoking history between diabetic and non-diabetic groups.
    c) Chi-Squared Test: Conducted a chi-squared test to determine the association between diabetes status and smoking history.
    d) Percentage Calculation: Calculated the percentage of each smoking status (current, former, never) for diabetics and non-diabetics.
    e) Visualization: Plotted smoking history percentages for diabetics and non-diabetics to visually compare the distributions.

Findings:

    a) The chi-squared test indicated a statistically significant association between diabetes status and smoking history.
    b) Former smoking status was higher for diabetics compared to non-diabetics.

![output](https://github.com/10H-K/diabetes/assets/152930492/0d0ad7ce-0ec9-4f0e-b90c-0d927d31ebeb)

Conclusion:
    
    The investigation found that individuals with diabetes are more likely to have a former smoking history compared to those without diabetes.
