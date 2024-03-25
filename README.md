# Call Centre Trend (Forage Virtual Internship)
## Problem Statement
In the course of this project we're tasked to create a dashboard for the call centre manager which reflect all the necessary Key Performance Indicators (KPI) and metrics in the dataset.
Suggested KPIs are as follows;
-Overall customer satisfaction.
-Overall calls answered/abandoned.
-Calls by time.
-Average speed of answer.
-Agent's performance quadrant; Average handle time (talk duration) vs calls answered.

## Data Source 
Dataset used were given by PWC. And it comprises of 10 columns and 5000 rows of observation. 

## Data Cleaning and Preparation
The dataset was uploaded and transformed in Power Query. As it was through rigorous we were able to accomplish the following outcome below;
-Removed Irrelevant rows and columns.
-Most of the columns were validated to ensure it has the befitting data type.
-Renamed Columns.
-Replaced certain values in some columns.

## Data Modeling
The dataset was classified into Measures and Columns to be able to provide the manager with the expected result.

## Data Analysis
list of Measures obtained in the prcocess of analysis:
-Average Satisfaction Rating = `AVERAGE(Sheet1[Satisfaction rating])`
-Average Speed of answer in seconds = `AVERAGE(Sheet1[Speed of answer in seconds])`
-Count of Satisfaction Rating = `COUNT('Sheet1'[Satisfaction rating])`
-Overall Customer Satisfaction = `DIVIDE([Positive Satisfaction Rating],[Count of Satisfaction Rating],0)`
-Positive Satisfaction Rating = `CALCULATE(COUNT('Sheet1'[Satisfaction rating]),FILTER('Sheet1','Sheet1'[Satisfaction rating] IN {4,5}))`
-Resoved Calls = `COUNTX(FILTER('Sheet1','Sheet1'[Resolved] = "Yes"),'Sheet1'[Resolved])`
-Total Calls = `CALCULATE('Sheet1'[Total Calls Answered] + 'Sheet1'[Total Calls Unanswered])`
-Total Calls Answered = `COUNTX(FILTER('Sheet1','Sheet1'[Answered (Y/N)] = "Yes"),'Sheet1'[Answered (Y/N)])`
-Total Calls Unanswered = `COUNTX(FILTER('Sheet1','Sheet1'[Answered (Y/N)] = "No"),'Sheet1'[Answered (Y/N)])`
-Unresoved Calls = `COUNTX(FILTER('Sheet1','Sheet1'[Resolved] = "No"),'Sheet1'[Resolved])`

## Data Visualization
Visualization being the dashboard was created in Microsoft Power Bi Desktop
![Dashboard](https://imgur.com/eL3ynu5)

## Insights
From the dashboard we can infer that
-Jim answered and at the same time recieved highest calls.
-Becky handled most of the call resolution.
-Diane and Jim together had the highest number of unresolved calls.
-Martha aced the speed of answer in seconds with a higher margin.
-Diane came top in the number of unanswered calls.
-Most calls emanated from streaming discourse.
-Diane had the greatest satisfaction rating compared to her contemporaries Jim and Martha.

