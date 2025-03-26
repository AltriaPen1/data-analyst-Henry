Table of Contents
Exploratory Data Analysis	3
Project Description:	3
Project Title:	3
Objective:	3
Dataset:	3
Methodology:	4
Tools and Technologies:	9
Descriptive Analysis	9
Project Description:	9
Project Title:	9
Objective:	9
Dataset:	9
Methodology:	10
Tools and Technologies:	18
Deliverables:	18
Diagnostic Analysis	19
Project Description: Diagnostic Analysis of Sales Decline at XYZ Retail	19
Project Title:	19
Objective:	19
Background:	19
Dataset:	19
Methodology:	20
Tools and Technologies:	21
Deliverables:	21
Timeline:	21
Data Wrangling	22
Project Description:	22
Project Title:	22
Objective:	22
Background:	22
Dataset:	22
Methodology:	23
Tools and Technologies:	25
Deliverables:	25
Timeline:	25
Data Quality Control	25
Project Description:	25
Project Title:	25
Objective:	25
Scope:	25
Methodology:	31
Deliverables:	32
Timeline:	32












Exploratory Data Analysis
Project Description: Exploratory Data Analysis (EDA) on DAP processing and summarizing bulk datasets required by the City of Vancouver
Project Title: AWS Data Analytic Platform for The City of Vancouver
Objective: The primary goal of this project is to perform exploratory data analysis (EDA) on the 311 contact center metrics dataset to design and implement a data analytic platform to support descriptive analysis. By analyzing various features such as Date, Calls_Offered, Calls_Handled, Calls_Abandoned, Average_Speed_of_Answer, Service_Level, and BI_ID, we aim to understand the factors that influenced the likelihood of the service of 311.
Dataset: This dataset consists of 311 service information, including details such as:
	Date: 2024-1-1 to 2025-1-31
	Calls_Offered: the time of 311 offering calls (seconds)
	Calls_Handled: the time of 311 handling calls (seconds)
	Calls_Abandoned: the time of 311 abandoning calls (seconds)
	Average_Speed_of_Answer: the time of average speed of answers from 311 (seconds)
	Service_Level: 311 service level (0-1)
	BI_ID: The ID number of providing services
When uploading the dataset in AWS, the data profile overview (see Figure 1) can show the summary of this dataset.
Figure 1: Data Profile Overview
 
Methodology:
1. Data Collection and Preparation and Cleaning:
	Download the dataset from the City of Vancouver
	Observing the initial dataset, which includes missing values, outliers, and data type.
	The initial data is mostly cleaning, so I just adjusted the two decimal places and then changed this dataset to a CSV file to be uploaded to AWS S3 Buckets (see figure 2 and figure 3)
Figure 2: S3 Bucket Building 
 
 Figure 3: Data Cleaning 
 
2. Descriptive Statistics:
All data are numerical values, but Service_Level and Average_Speed_of_Answer are not integers. 
3. Data Cataloging:
I created a new bucket called 311-ctc-mtr-cur and sub-folders for metrics including system and user folders, which will be stored for summarization. When the Crawler was ready, the cleaning data was transferred to databases for 34 cataloging and prepared for summarization (See Figure 4, Figure 5, Figure 6). 
Figure 4: Metrics Folders Building
 
Figure 5: Crawlers Building
 
Figure 6: Transfer Cleaning Data to Databases for Catalog
 
4. Data Summarization:
Two ETL pipelines were established, and the metrics report was for systems and users.
Figure 7: ETL Pipeline
 
Figure 8: Metrics Report
 
5. Conclusion:
This project designed and implemented a data analytic platform that supports descriptive analysis and provided a thorough report that breaks down each step of the process. City of Vancouver can leverage AWS to drive data-based decision-making with minimal cost and high efficiency
6. Data Cleaning (in-class activity):
Table 1: Poor Data Quality Dataset
 
In this class activity, we practiced identifying the poor data quality including duplicate, missing values, invalid values, inconsistent format, unbalanced, typo, encoding, and so forth. 
Tools and Technologies:
AWS S3, Glue, Glue DataBrew
Descriptive Analysis 
Project Description: Descriptive Analysis of Sales Performance (W6 in-class)
Project Title: Understanding the Sales Performance
Objective: Questions about Sales Performance Analysis, Impact of Marketing Spend, Effect of Temperature on Sales, and Website Traffic Insight were answered. 
Dataset: The dataset includes the following key features:
	Date: 2023-1-1 to 2024-3-31
	Sales: Sales of each corresponding date
	Temperature: the temperature of each corresponding date
	Marketing Spend: the expenditure on the marketing of each corresponding date
	Customer purchase behavior: there are three categories, including A,B, and C.
	Website Traffic: the amount of traffic of each corresponding date
	Outlier Flag: there are two 
Table 2: Sales Performance Dataset
 
Methodology:
1. Data Collection and Preparation:
	Load the dataset using data analysis tools, including Excel and SQL
	The original data is cleaned.
2.1 Descriptive Statistics:
Table 3: Questions about Sales Performance Analysis, SQL Syntax, and Analysis
 
Calculate summary statistics for key variables, including:
	Average sales
	The highest and lowest sales 
	How do sales vary by date
3.1 Data Visualization:
Table 4: Data Visualization by Excel
 
Create visual representations to illustrate findings:
	Average sales: 139.0625
	The highest sales: 300
	The lowest sales: 50
	Sales vary in each date
2.2 Descriptive Statistics:
Table 5: Questions about Impact of Marketing Spend, SQL Syntax, and Analysis
 
Calculate summary statistics for key variables, including:
	Correlation between marketing spend and sales
	The correlation between marketing spend and website traffic
	Which dates had the highest and lowest marking spending
3.2 Data Visualization:
Table 6: Data Visualization by Excel
 
Create visual representations to illustrate findings:
	Correlation between marketing spend and sales: 0.313434298
	Correlation between marketing spend and website: 0.318149461
	The highest marketing spend date: 2023-3-15
	The lowest marketing spend date: 2023-1-1
2.3 Descriptive Statistics:
Table 7: Questions about Effect of Temperature on Sales, SQL Syntax, and Analysis
 
Calculate summary statistics for key variables, including:
	Correlation between temperature and sales
	Does higher temperatures lead to more or fewer sales?
3.3 Data Visualization:
Table 8: Data Visualization by Excel
 
Create visual representations to illustrate findings:
	Correlation between temperature and sales: 0.701793526
	When the temperature is higher, the average sales are higher.
2.4 Descriptive Statistics:
Table 9: Questions about website traffic insights, SQL Syntax, and Analysis
 
Calculate summary statistics for key variables, including:
	What is the average daily website traffic?
	On which dates was the website traffic highest and lowest?
	Does an increase in website traffic lead to higher sales?
3.4 Data Visualization:
Table 10: Data Visualization by Excel
 
Create visual representations to illustrate findings:
	The average daily website traffic: 985.625
	The highest website traffic is 2500 on 2023-2-29
	The correlation between website traffic and sales: 0.224236537 
4. Insights and Findings:
	The highest correlation of sales is the temperature, and the higher the temperature is, the higher the sales are.
	The highest sales happened in March, so marketing spending was also used most in this month.
5. Recommendations:
	The sales rely more on the temperature, so adjusting the suitable temperature in the store is essential, although the outside temperature cannot be controlled.
	The marketing expenditure can be reduced gradually, particularly in the month with higher sales.
6. Other Descriptive Analysis (Weekly Activity 6)
Figure 9. Using Athena to Do descriptive Analysis 
 
 
 
Tools and Technologies:
	SQL and Excel for data analysis, and AWS Athena for descriptive data analysis
	Data visualization tool is Excel
Deliverables:
•	A detailed report summarizing the methods, findings, and recommendations.
•	Visualizations and dashboards to present key insights clearly.
•	A presentation for stakeholders to communicate important findings and suggestions for future action.
This descriptive analysis project aims to comprehensively understand sales performance, the impact of marketing expenditures, the impact of the temperature on sales, and the website traffic insights.
Diagnostic Analysis 
Project Description: Diagnostic Analysis of Sales Decline at XYZ Retail
Project Title: Investigating the Causes of Sales Decline at XYZ Retail
Objective: The primary goal of this project is to conduct a diagnostic analysis to identify the underlying causes of a recent decline in sales at XYZ Retail. By analyzing various data sources, we aim to uncover the factors contributing to this decline and provide actionable insights for management to formulate effective strategies for improvement.
Background: Over the past six months, XYZ Retail has experienced a noticeable decline in sales, which has prompted management to seek a thorough understanding of the reasons behind this trend. This analysis will not only help in identifying contributing factors but also guide remedial actions to reverse the decline.
Dataset: The analysis will utilize multiple datasets, including:
•	Sales Data: Daily sales transactions from the past year, including product categories, transaction amounts, and customer demographics.
•	Inventory Data: Records of stock levels for each product category over the same period, indicating any shortages or overstock situations.
•	Customer Feedback: Survey data and feedback directly from customers regarding their shopping experiences, preferences, and complaints.
•	Market Data: External factors, including regional economic indicators, competitor pricing, and market trends.
Methodology:
1-	Data Collection and Preparation:
o	Consolidate and clean datasets from multiple sources to ensure accuracy and consistency.
o	Normalize data to make it suitable for analysis.
2-	Trend Analysis:
o	Perform a thorough analysis of sales trends over the last year to identify specific periods and product categories where declines were most significant.
3-	Correlation Analysis:
o	Identify correlations between sales decline and other variables, such as inventory levels, customer feedback, and market conditions.
o	Use statistical methods (like regression analysis) to quantify how strongly these factors influence sales.
4-	Root Cause Analysis:
o	Conduct focus group discussions or interviews (if feasible) with store staff and management to gather qualitative insights on observed changes in customer behavior and inventory practices.
o	Utilize techniques such as the "5 Whys" or Fishbone Diagram to systematically investigate potential causes.
5-	Segmentation Analysis:
o	Segment customers based on behaviors (e.g., frequency of purchase, average transaction size) to analyze differing impacts across segments.
6-	Synthesis of Findings:
o	Integrate quantitative and qualitative data to uncover patterns and themes that indicate the most significant factors contributing to the sales decline.
Tools and Technologies:
•	Data analysis tools (Python with libraries like Pandas and Scikit-learn, R, or SQL) for metrics calculations and correlation analysis.
•	Visualization tools (Tableau or Power BI) for presenting findings and trends clearly to stakeholders.
Deliverables:
•	A comprehensive diagnostic report that outlines the analysis process, findings, and confirmed root causes of the sales decline.
•	Visualizations and dashboards summarizing key metrics and trends.
•	Actionable recommendations for management, focusing on strategies to address identified issues and improve sales performance.
Timeline:
•	Expected completion of the project: 6 weeks from project kickoff, including regular check-ins with stakeholders to align findings and recommendations.
This diagnostic analysis aims to provide a clear understanding of the reasons behind the decline in sales at XYZ Retail, enabling management to take targeted actions to boost revenue and enhance customer satisfaction in the future.

Data Wrangling 
Project Description: The City of Vancouver needs to migrate to AWS, and we implemented a data analytic platform.
Project Title: AWS Data Analytic Platform for The City of Vancouver
Objective: The primary goal of this project is to perform comprehensive data wrangling to prepare a robust dataset for the 311 Contact Center at The City of Vancouver. By cleaning, transforming, and consolidating data from various sources at AWS, the project aims to enhance the accuracy and usability of this data for subsequent analysis and reporting.
Background: The City of Vancouver needs to migrate its data to AWS, and I selected one of the datasets about the 311 Contact Center. However, this data needs cleaning, otherwise making it challenging to derive meaningful insights. Effective data wrangling will facilitate better decision-making.
Dataset: The data wrangling process will involve one dataset, including:
	Date: 2024-1-1 to 2025-1-31
	Calls_Offered: the time of 311 offering calls (seconds)
	Calls_Handled: the time of 311 handling calls (seconds)
	Calls_Abandoned: the time of 311 abandoning calls (seconds)
	Average_Speed_of_Answer: the time of average speed of answers from 311 (seconds)
	Service_Level: 311 service level (0-1)
	BI_ID: The ID number of providing services
Methodology:
1. Data Collection:
	Download the dataset from the City of Vancouver
	Observing the initial dataset, which includes missing values, outliers, and data type.
2. Data Assessment and Cleaning:
Figure . Quality Check in Visual ETL
 
I did the ruleset for data quality and then set the conditional router, including passed and failed, and then changed the schema before load, including dropping the useless columns. Finally, I loaded the Passed and Failed into the corresponding folders. 
3. Data Transformation and Consolidation:
Figure : Failed Dataset in Transfer Bucket
 
Figure : Passed Dataset in Transfer Bucket
 
After loading the passed and failed in Visual ETL, the corresponding datasets have already been published into each sub-bucket in the transfer bucket, which can be downloaded for different uses.
Tools and Technologies:
	AWS S3 and AWS Glue
Deliverables:
	A cleaned and transformed 311 Contact Center dataset ready for analysis, particularly for Passed Dataset in a CSV format.
	Confirmation of data quality checks conducted during the process.
Timeline:
	Expected completion of the project: Week 9 and Week 10, including phases for assessment, cleaning, transformation, and documentation.
This data wrangling project aims to establish a high-quality dataset that enables the City of Vancouver to conduct adequate 311 Contact Center Data.
Data Quality Control
Project Description: The HR Department of UCW implemented the Data Quality Control
Project Title: Implementation of Data Quality Control Measures HR Department of UCW
Objective: The primary objective of this project is to establish a comprehensive Data Quality Control (DQC) framework at AWS for the HR department of UCW. This framework will ensure the organization's data's accuracy, completeness, consistency, and reliability, enhancing decision-making processes and overall business performance.
Scope: The project will focus on the following key areas:
	Data Profiling: Analyzing existing datasets to assess quality levels.
Figure : Data Profiling for HR of UCW
 
 
 
	Data Cleansing: Developing processes to correct inaccuracies and eliminate duplicates.
Figure : Data Cleaning for HR of UCW
 
 
 
	Data Validation: Implementing validation rules and checks to ensure data integrity.
Figure : Data Validation for HR of UCW
 
 
 
	Monitoring and Reporting: Establishing ongoing monitoring processes and dashboards to track data quality metrics.
Figure : Data Monitoring for HR of UCW
 
 
Methodology:
1. Data Profiling:
	Utilize data profiling tools to assess the quality of identified datasets, focusing on completeness, uniqueness, validity, consistency, and accuracy.
	Document findings to highlight areas requiring immediate attention.
2. Data Cleansing Processes:
Develop and implement procedures for data cleansing, which includes renaming.
3. Validation Rules and Procedures:
	Set up validation rules for new data entries to reduce the risk of poor-quality data being introduced into the system.
	Create data entry guidelines to promote consistency and accuracy.
4. Monitoring:
	Implement monitoring tools and dashboards that provide real-time data quality metrics and alerts for significant deviations.
Tools and Technologies:
	AWS CloudWatch
	WAS Glue DataBrew
Deliverables:
	A comprehensive Data Quality Control plan detailing processes, metrics, and responsibilities.
	Cleaned and validated datasets ready for analysis and reporting.
	A monitoring dashboard that visualizes data quality metrics in real time.
Timeline:
Expected completion of the project: Week 3, Week 4, and Week 9.
This Data Quality Control initiative aims to empower UCW to enhance its HR data integrity and reliability, resulting in improved decision-making, operational efficiency, and compliance with regulatory requirements.

