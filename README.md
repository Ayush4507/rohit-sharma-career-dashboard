🏏 Rohit Sharma Career Dashboard — Power BI

An end-to-end Power BI dashboard analyzing international batting career performance across ODI, T20I, and Test formats, built on a single Batting Data fact table.


📌 Overview

This dashboard tracks career-level batting performance with dynamic filtering by format, opponent, match result, date, and venue — covering run totals, milestones, strike rate, boundary contribution, and match outcomes in one interactive view.

Note: This project currently uses illustrative sample data for demonstration purposes. Figures are not verified real-world career statistics.

🎯 Features
11 KPI cards: Total Runs, Matches, Innings, 50s, 100s, Highest Score, Fours, Sixes, Strike Rate, Not Outs, Matches Won
5 interactive slicers: Format, Opponent, Match Result, Date range, Venue
7 visuals: Runs by Format, Runs by Year (trend), 50s vs 100s by Format, Runs vs Balls Faced (scatter), Top Opponents by Runs, Boundary Analysis (combo chart), Match Results (donut)
Career Summary table: format-wise breakdown of Matches, Innings, Runs, Average, Strike Rate, 50s, 100s, Highest Score
Custom dark theme: navy background with blue/teal/gold accent palette
🧮 Key DAX Measures
dax
Total Runs = SUM('Batting Data'[Runs])
Total Matches = DISTINCTCOUNT('Batting Data'[Match_ID])
Total Innings = COUNTROWS('Batting Data')
Total 50s = COUNTROWS(FILTER('Batting Data', [Runs] >= 50 && [Runs] < 100))
Total 100s = COUNTROWS(FILTER('Batting Data', [Runs] >= 100))
Highest Score = MAX('Batting Data'[Runs])
Strike Rate = DIVIDE(SUM('Batting Data'[Runs]), SUM('Batting Data'[Balls_Faced])) * 100
Total Matches Won = CALCULATE(DISTINCTCOUNT('Batting Data'[Match_ID]), 'Batting Data'[Match_Result] = "Won")
🛠️ Tools & Skills
Power BI Desktop
DAX (Data Analysis Expressions)
Data modeling (star-schema style single fact table + date table)
Custom theme design (JSON theming)
Data visualization design principles
📂 Repo Contents
File	Description
Rohit_Sharma_Career_Dashboard.pbix	Main Power BI report file
Batting_Data_Sample.xlsx	Sample dataset matching the report's data model
Cricket_Theme.json	Custom Power BI theme file
🚀 How to Use
Clone or download this repo
Open the .pbix file in Power BI Desktop
(Optional) Apply the theme: View > Themes > Browse for themes → select Cricket_Theme.json
Explore the report using the slicers on the page
