<img src= analysis.png alt="Example Image" width="300">

# Cricket-Test-Match-Data-Analysis-Python-Project
# Project Overview
This project focuses on cleaning and analyzing Test match cricket data to extract meaningful insights. It involves handling missing values, correcting data types, detecting duplicates, and structuring the dataset for further analysis.
.
# Key Objectives

# 1️. Handling Missing Values

Identify missing data in the dataset.
Fill missing Ball_Faced Column values using the filna function with 0.
Fill missing Batting_Strike_Rate Column values using the filna function with 0.

# 2️. Removing Duplicates
Detect and remove duplicate rows to maintain data integrity.

# 3️. Fixing Data Inconsistencies

change column names (e.g.,NO column convert into Not_Outs, Mat column convert into Matches).
Correct inconsistent formats in numeric, and categorical data.

# 4️. Handling Incorrect Data Types

Convert columns to appropriate data types (e.g., Highest_Runs to float64, numeric to integers/floats).

# 5️. Parsing and Splitting Data

Extract meaningful information (e.g., splitting player names and countries).

# 6️. Removing Unnecessary Data

Drop irrelevant or redundant columns that don’t contribute to analysis.

# Feature Engineering
Create new column  Initial_Year spilt the span Coulumn. 
Create new column  Final_Year spilt the span Coulumn. 
Create new column  Career_Length  Using initial_Year and Final_year  Column.

# Technologies Used
Python (python, or SQL Server) – for data extraction, transformation, and analysis.
Excel / Power BI / Tableau (Optional) – for visualization and dashboard reporting.

## About Data

This project's data was obtained from the  website espncricinfo of Test match data extract from Using link [text](https://www.espncricinfo.com/records/highest-career-batting-average-282910)
The data contains 18 columns and 61 rows:
| Column            | Description                                   | Data Type        |
|-------------------|-----------------------------------------------|------------------|
| Player            | Gives player name                             | object           |
| Matches           | Gives the number matches over played by player| int64            |
| Inns              | Innings played by players                     | int64            |
| Not_Outs          | How much times player remain not out          | int64            |
| Runs              | How much runs total scored by player          | int 64           |
| Highest_Runs      | Invidiual highest scored run in one Inning    | int64            |
| Average           | The average run scored in batting             | float64          |
| Ball_Faced        | Total ball played by players                  | int64            |
|Batting_Strike_Rate| Total run scored by per ball                  | float64          |
| 100               | How many times scored 100 runs                | int64            |
| 0                 | How many times scored Zero runs               | int64            |
| 4s                | How many times played 4 runs                  | int64            |
| 6s                | How many times played 6 runs                  | int64            |
| Initial_Year      | Gives the year when start the career          | int64            |
| Final_Year        | Gives the year when retired from career       | int64            |
| Country           | Gives the player Country name                 | object           |
| Career_Length     | Gives the player career span in Year          | int64            |

.

# Conclusion
The Test Match Data Cleaning Project successfully refined and structured raw cricket data, making it more reliable for analysis. By renaming columns, handling missing values, and removing duplicates, the dataset was transformed into a clean and consistent format. These preprocessing steps ensure better accuracy in statistical analysis and predictive modeling of player performances.

This cleaned dataset can now be effectively used for further data visualization, trend analysis, and advanced cricket analytics.

## Questions to Answer

# Q.1 What is the average Career length
Ans: df['Career_Length'].mean()

# Q.2 Average Batting_Strike_Rate for cricketers who played over 10 years
Ans: df[df['Career_Length'] > 10]['Batting_Strike_Rate'].mean()

# Q.3 Find numbers of cricketer who played before 1960
Ans: df[df['Initial_Year'] < 1960]['Player'].count()

# Q.4. Max Highest Runs Scored By Country
Ans: df.groupby('Country')['Highest_Runs'].max().to_frame(name='HighestRunsCountry').reset_index().sort_values('HighestRunsCountry', ascending=False) 

# Q.5 Hundreds,fifties, ducks(0) avg by Country
Ans: df.groupby('Country')[['100', '50', '0']].mean()

