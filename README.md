# Bank-Churn-Customer-Analysis
## Analysing the Root Cause of Customer Churn Behaviour

![Dashboard](https://github.com/EEmilyA/Bank-Churn-Customer-Analysis/blob/main/Demograph.png)
![Dashboard](https://github.com/EEmilyA/Bank-Churn-Customer-Analysis/blob/main/Correlation.png)

## Introduction
This report analysis an unknown Bank to understand why in recent times, there have been massive churn of customer activities with the bank. It analysis key metrics, to understand the why and possible root cause and profer solutions to the bank stakeholders in order to curb this massive setback the bank is facing.

## Data source
The data source for this dataset was shared from Evergreen Digital boothcamp and workshop session from youtube channel. 

## Problem Statement
"Why do we have masssive redundancy of our bank customers?!"
In recent months, The audit team has noticed a massive redundancy and customer accounts closure. This has amounted to unanswered questions like; Are they unhappy with our services, or are competitors winning their hearts?. This project aims to answer these questions and uncover the secret patterns behind customer churn by digging into their demographics, behaviors, complaints, satisfaction scores, and product usage. This analysis will uncover who’s leaving, why they’re leaving, and what we can do to keep them!

## Pre-Analysis Questions
1. Who are our churned customers?:(Age groups, credit scores, gender, geography, and card types)
2. Is there a link between churn and satisfaction scores or complaints?
3. Do customers with low product engagement tend to churn more?
4. Does having a credit card or being an active member reduce churn?
5. Are high earners or those with higher balances more loyal?
6. What role does tenure play in churn likelihood?
7. Which card types are more prone to churn?
8. Are there any geographic regions with higher churn rates?
9. Does churn correlate with the number of points earned or card usage?
10. Can we identify a customer churn risk profile for early detection?

## Key Metrics For Analysis
1. Churn Rate (%) = (Number of churned customers / Total customers) × 100
2. Churn Rate by Geography
3. Average Credit Score of Churned vs Retained Customers
4. Satisfaction Score Distribution by Churn Status
5. % of Churned Customers with Complaints
6. Tenure vs Churn Rate
7. Product Holding and Churn Correlation
8. Card Type Churn Rate
9. Active Membership and Churn Rate
10. Estimated Salary Comparison: Churned vs Retained.

## DATA CLEANING AND PREPARATION
### Step1: Data 
- The data was imported into Excel sheet and converted into a table, duplicatates, Null values, and outliers where checked to ensure data integrity and consistency.
- A new calculated column for age_range was created to better understand the age group of customers who were prone to leaving the bank.
- Pivot table was inserted to for our exploratory data analysis and new measures were created for the follwing additional metrics:
 1. Total Chun's Customers and Retained customers
   - Retained Customer=CALCULATE([Total_Customers],Customer_Churn_Records_263[Exited]=0)
   - Churned Customer=CALCULATE([Total_Customers],Customer_Churn_Records_263[Exited]=1)
 2. Total customer =COUNTROWS(Customer_Churn_Records_263)
 3. Retention Rate =DIVIDE([Retained_Customers],[Total_Customers],0)
 4. Churnned Rate =DIVIDE([chun_Customers],[Total_Customers],0)
 5. Average Satisfaction =AVERAGE(Customer_Churn_Records_263[Satisfaction Score])
 6. Average Tenure = AVERAGE(Customer_Churn_Records_263[Tenure]).
 7. Correlation coefficient of Age and churn rate = correl( range of Age, range of Churn Rate)
 8. Max Shun country =XLOOKUP(MAX($K$25:$K$27),K25:K27,J25:J27)
 9. Percentage of churn by  country =INDEX(K25:K27,MATCH(MAX(K25:K27 country),K25:K27 Values,0))
 10. Average Bal before chun =CALCULATE(AVERAGE(Customer_Churn_Records_263[Balance]),Customer_Churn_Records_263[Exited]=0)


### Step2: Exploratory Data Analysis.
1. Customer Overview:
Total Customers: 10,000 , Retained Customers: 7,982 (79.82%), Churned Customers: 2,018 (20.18%), Average Satisfaction Score: 3.9/5 Average Age: 39 years,and Average Tenure: 5 years.
2. Churn by Demographics:
   - Gender:Female churn rate: 25.96%, and Male churn rate: ~18.47%
   - Age: Churn higher among middle-aged customers (40–50 years old).
   - Location: Geographic variation in churn rate.

## Insights and Recommendations
- Churn by Age: Higher coefficient (0.50) suggests age is positively correlated with churn rate
- Churn by Geography: Germany shows significantly higher churn compared to Spain and France, suggesting a potential issue specific to this region.
- Churn by Average Balance:Customers with higher average balances are more likely to churn, indicating that higher-value customers may require targeted retention strategies.
- Churn by Number of Products:Lower product holdings (1-2 products) are associated with lower churn rates, while higher product holdings (3-4 products) correlate with significantly elevated churn. This trend may imply that customers with more products experience unmet needs or service issues, warranting targeted retention strategies for these segments.
- Churn by Tenure Analysis: Although the churn rate decreases modestly with longer tenure, churn remains present across all tenure levels. The slight improvement at 7+ years suggests that further incentives and loyalty programs could stabilize and reduce churn more effectively for long-standing customers.
- Churn by Satisfaction Score Analysis:The similar churn rates across satisfaction scores suggest that while satisfaction impacts churn, other factors may play a larger role. However, targeted improvements for scores 2 and 4 may help reduce churn within those segments.
- Churn by Gender: Female customers show a significantly higher churn rate than male customers (25.07% vs. 16.47%). This indicates a potential need for gender-specific engagement strategies to address the higher churn risk among female customers.
- Churn by Card Type: Diamond cardholders have the highest churn rate (21.78%), whereas Gold cardholders have the lowest (19.26%). This suggests a potential need to reassess benefits or engagement strategies for higher-tier card types to reduce churn.
- Churn by Credit Score Analysis: Customers with lower credit scores are more likely to churn. This relationship could imply that financial stability, as reflected by a higher credit score, may increase customer retention. Targeted strategies for customers with lower credit scores might help in reducing churn rates further
- #### Churn by Complaint: This sharp contrast highlights that customers who complain are highly likely to churn. The data suggests that addressing complaints might significantly reduce churn rates. Further investigation into the nature of these complaints could provide actionable insights for retention strategies.
To reduce churn, strategies should focus on:
1. Proactive complaint resolution
2. Targeted engagement for high-risk demographics and geographies
3. Loyalty programs for long-standing customers.
4. Tailored offerings and improved service for high-value customers
5. Addressing these factors holistically can improve customer retention and strengthen overall relationship management.

## Conclusion
The churn analysis indicates that customer Churn is driven by a combination of demographic, geographic, financial, and service-related factors. Older customers, females, German customers, those with higher account balances, more products, lower credit scores, and  more sIgnificantly, from customers who submit complaints.



