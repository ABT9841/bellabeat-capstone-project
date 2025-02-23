# Bellabeat-Capstone-Project
This repository contains the Bellabeat case study as part of my data analytics portfolio. The project focuses on analyzing smart device usage data to provide actionable insights for a wellness brand. Tools used: SQL, Excel, Google Slides, and Tableau for data cleaning, analysis, and visualization.

# Bellabeat Smart Device Usage Data Analysis

## Project Overview

### Business Task:
The goal of this analysis is to provide insights into how consumers use non-Bellabeat smart devices (specifically Fitbit data) to help Bellabeat make data-driven business decisions. The analysis focuses on understanding user activity patterns and providing recommendations for improving user engagement with the Bellabeat app.

### Dataset: From Kaggle https://www.kaggle.com/datasets/kyle007hendricks/bellabeat-dataset
### Dataset Overview:
The dataset consists of data from **33 individuals** over the course of **one month**, collected via Fitbit devices. The data includes various activity metrics such as step count, heart rate, intensity, calories burned, and more. The dataset has several limitations:
- **Small sample size** of only 33 individuals.
- **Short duration** of just one month.
- Missing **demographic information** such as gender.
- Data is limited to **Fitbit** devices, excluding other smart devices users may have.
- Fitbit users may already be health-conscious, which might skew results.

---

## Data Preparation & Cleaning

## SQL Queries
The SQL queries used in this project are organized into different files based on their purpose:

- [data_cleaning.sql](https://github.com/ABT9841/bellabeat-capstone-project/blob/main/DATA%20CLEANING(%20CREATING%20A%20NEW%20TABLE)): Queries for cleaning the raw data and created a table
- [data_analysis.sql](https://github.com/ABT9841/bellabeat-capstone-project/blob/main/ANALAYIZING%20(NUMBER%20OF%20USERS%20AND%20DAILY%20AVERAGES)): Queries to calculating number of users and daily avaerages
- [data_analysis.sql](https://github.com/ABT9841/bellabeat-capstone-project/blob/main/DATA%20ANALYZING%20(DAYS%20EACH%20USER%20TRACK%20PHYSICAL%20ACTIVITY)): Queries to calculate the number of days each user tracked physical activity
- [data_analysis.sql](https://github.com/ABT9841/bellabeat-capstone-project/blob/main/ANALYZE%20(ACTIVE%20TIME)): Queries to determine time when users were mostly active



### 1. Importing and Merging Data:
The data was imported using **SQL Server Management Studio (SSMS)** for large-scale cleaning, and **Excel** was used for merging multiple sheets into a single dataset. 

- **Steps Taken:**
  - Imported various raw CSV files (hourly activity, steps, intensity, calories, etc.).
  - Used **Power Query** in Excel to merge data and ensure all relevant columns were included in one sheet.
  - Saved the clean dataset into an Excel file (`Hourly_Activity.xlsx`) for further analysis.

### 2. Data Import into SQL Server:
Once the data was cleaned and merged, it was imported into **SQL Server Management Studio (SSMS)**:
- **Files Imported:**
  - `daily_activity_merged`
  - `heartrate_seconds_merged`
  - `weight_info_log`

- **Data Type Adjustments:**
  - Unticked data type detection to avoid errors from incompatible values.
  - Manually changed some columns (e.g., activity minutes, total steps) to `INT` type and `calories` to `FLOAT` based on the data's content.
  - Ensured that `NULL` values were allowed for non-critical columns, except for the ID column.

### 3. Data Cleaning:
Once imported, I created cleaned versions of the data to improve data quality:
- **Created New Tables:**
  - `DAILY_ACTIVITY_CLEANED`: Inserted cleaned values from the daily activity dataset.
  - `WEIGHT_INFO_CLEANED`: Cleaned weight info by removing unnecessary columns and retaining relevant ones.

---

## Data Analysis

### 1. Activity Analysis:
The analysis aimed to understand the activity patterns of users by calculating key metrics such as:
- **What Activity** is tracked most by user.
- **Average Intensity** for each hour of the day.
- **Correlation between activity and calories burned.**
- **Identifying the most active times** of the day for users.

- **SQL Operations:**
  - Used the `OVER` clause with `PARTITION BY` to calculate the average intensity for each hour of the day.
  - Joins were made between the `hourly_activity` and `minutesMETsNarrow` tables to analyze activity intensity and calories burned.

### 2. Key Findings:
- **People Tracking Activity:** People mostly tracked the physical activity more than any other activity.
- **Peak Activity Time:** Users were most active around **6 PM** each day, while the least active time was around **3 AM**.
- **Intensity and Calories Burned:** Higher activity intensity was strongly correlated with increased calories burned. This suggests that users engaging in more intense activity are burning more calories.
- **Sedentary Behavior:** The data revealed that **81% of users' time was sedentary**, indicating a need for improved strategies to combat inactivity.
- **Positive Correlations:**
  - **Activity level vs. Calories burned:** More activity leads to more calories burned.
  - **Intensity vs. Calories burned:** Higher intensity activities result in more calories burned.

---

## Business Recommendations

Based on the findings from the analysis, here are several recommendations for Bellabeat:

1. **Expand Sample Size:** Collect data from a larger sample size to improve the robustness of insights and ensure diversity in activity patterns.
2. **Focus on Key Activities:** Focus efforts on **physical activity** and **sleep tracking** as they are the most engaged features in the app.
3. **Evening Engagement:** Since users are most active around 6 PM, Bellabeat should send **activity prompts or reminders** during the evening to encourage continued engagement.
4. **Combat Sedentary Behavior:** Introduce **pop-up notifications** to encourage users to move, as a large portion of users is sedentary for long periods.
5. **Reward System:** Implement a **points-based reward system** that users can redeem for Bellabeat products or memberships, encouraging continued engagement.
6. **Personalization & Gamification:** Offer **personalized insights** and **gamified challenges** to increase motivation and user interaction with the app.
7. **Community & Premium Features:** Foster a **social community** feature within the app and promote **premium features** through insights and rewards.

---

## Data Visualization

### Tools Used:
- Link: https://public.tableau.com/views/BellabeatProject_17370932150140/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
- **Tableau** was used to visualize the data and communicate the insights in an easily digestible format.
- ![Tableau Dashboard](TABLEAU.png)


### Visualizations Created:
- **Hourly Activity Patterns:** A visualization of activity levels throughout the day to highlight peak times (6 PM) and low activity times (3 AM).
- **Activity Intensity vs. Calories Burned:** A chart showing the correlation between intensity and calories burned.
- **Sedentary Time:** A visualization demonstrating the large portion of users' time spent in sedentary behavior.
- **Engagement & Activity Trends:** An interactive dashboard showing the most active times, average days of activity, and user behavior over time.

---

## Conclusion

This project demonstrates the ability to clean, analyze, and derive actionable insights from consumer activity data. By focusing on key metrics such as activity levels, intensity, and calories burned, it provides valuable recommendations for Bellabeat to improve user engagement and optimize the app experience. Further steps include expanding the sample size and collecting more data to refine the analysis and continue improving business strategies.

---

## Acknowledgements
- Dataset provided by [Kaggle](https://www.kaggle.com/).
- Special thanks to [Google Data Analytics Certificate](https://www.coursera.org/professional-certificates/google-data-analytics).


