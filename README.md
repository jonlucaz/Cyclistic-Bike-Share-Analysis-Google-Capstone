# Cyclistic Bike-Share Case Study  
**How does a bike-share navigate speedy success?**  
*Google Data Analytics Capstone Project*

---

## Project Objective
The objective of this project is to analyze how casual riders and annual members use Cyclistic bikes differently. The goal is to provide data-driven insights that support the design of a targeted marketing strategy aimed at converting casual riders into annual members, thereby increasing the company’s revenue and long-term customer base.

---

## Ask Phase

- **Central Problem**: Understand how annual members and casual riders differ in their usage of Cyclistic bikes.  
- **Objective**: Analyze usage data to identify behavioral differences between the two user groups.  
- **Data Source**: Historical trip data provided by Cyclistic.  

**Key Questions:**
- How do annual members use the bikes in terms of volume, time of day, and seasonality?
- How does this differ from casual riders across the same variables?

---

## Prepare Phase

**Initial Steps:**
- Downloaded 12 months of trip data (June 2024 – May 2025).
- Used **Excel** for cleaning and exploring the data.
- Each dataset includes 13 columns (ride times, stations, rider type, etc.).

**ROCCC Principles Check:**
- **Reliable**: Data from Motivate International Inc. (Divvy operator).
- **Original**: Primary source data.
- **Comprehensive**: 12 months of data with seasonal patterns.
- **Current**: Most recent data available.
- **Cited**: Public dataset from Divvy’s website.

**Bias & Credibility Considerations:**
- Data is anonymized (no personal info), limiting behavioral insights.
- No demographic data (e.g., age, gender, income) is available.

**Data Cleaning Notes:**
- Timestamps had milliseconds that interfered with Excel formatting.
- Removed last 4 characters from timestamp fields using:
  `=LEFT(D2, LEN(D2) - 4)`
- Calculated `trip_duration` (ended_at - started_at).
- Found 43 rides with negative durations in November 2024 and removed them.

---

## Process Phase

- Renamed `trip_duration` column to `ride_length`.
- Created `day_of_week` column using:
  `=TEXT(C2, "dddd")`
- Continued using Excel for processing due to familiarity and flexibility.
- Removed rows with negative durations.
- Data was cleaned and prepared for analysis.

---

## Analyze Phase

- Due to Excel's row limit, full dataset aggregation wasn't possible in a single table.
- Used **Pivot Tables** in each of the 12 worksheets.
- Manually aggregated results into a summary sheet.
- Replaced weekday numbers with names (e.g., Monday) for readability.
- Created two pivot tables per month in a sheet named "Dynamics":
  - Avg. ride length by `member_casual` × `day_of_week`
  - Total ride count by `member_casual` × `day_of_week`

---

## Share Phase

- Built two summary tables using:
  - `=AVERAGE(...)` for ride length
  - `=SUM(...)` for ride count
- Created **bar charts** to visualize:
  - Average ride duration
  - ![Average Ride Length Chart](https://github.com/jonlucaz/Cyclistic-Bike-Share-Analysis-Google-Capstone/blob/main/number_ride.png)
  - Number of rides
  - ![Ride Count Chart](https://github.com/jonlucaz/Cyclistic-Bike-Share-Analysis-Google-Capstone/blob/main/ride_length.png)

**Key Insights:**
- Annual members ride more consistently on weekdays → likely for commuting.
- Casual riders ride more on weekends; usage increases on Fridays → leisure usage.

---

## Act Phase

**Key Conclusions:**
1. **Annual members** take more rides, but **casual riders** have longer durations.  
   → Consider time-based discounts for members.

2. Annual usage patterns suggest commuting.  
   → Marketing campaigns could target casual riders with commute-related benefits.

3. Casual use is low Mon–Thu, especially in duration.  
   → Offer weekday promotions to increase engagement.

---

## Wrap-Up

This project was a rewarding challenge. Although structured, the large dataset caused issues with Google Sheets, so I switched to Excel.

I chose spreadsheets to strengthen my formula and function skills, but Excel's row limitations forced me to summarize results manually using Pivot Tables.

This limited my ability to perform deeper analysis across months.

**Lesson learned:** Future projects would benefit from a hybrid approach — using **Excel for cleaning**, and **R or SQL** for aggregation, analysis, and visualizations at scale.

---

**Files Included**:
- 
