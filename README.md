# ***Chicago Crime Data Analysis***

## **Overview**
This project presents an end-to-end exploratory analysis of crime data in the city of Chicago. The objective is to uncover meaningful insights into crime patterns across time, location, and severity. The work emphasizes:
- spatial crime distribution across communities and wards
- temporal crime trends at daily, monthly, and yearly levels
- classification of crimes based on severity
- robust data cleaning and preprocessing for downstream analytics and visualization

The resulting cleaned dataset is optimized for dashboarding tools such as Power BI and Tableau, as well as further statistical or machine-learning analysis.

## Data Processing Methodology

### **Time-Based Feature Engineering**
To enable trend and seasonality analysis:
- extracted components such as Date, Time, Day, Month 
- created DayOfWeek to study weekday vs weekend patterns
- standardized date-time formats to ensure consistency
- prepared data for time-series aggregation

These engineered features help identify peak crime hours, seasonal spikes, and weekday trends.

### **Data Cleaning**
1. *Missing Value Treatment*
  - Coordinates (X, Y, Latitude, Longitude): Dropped rows (1.26% missing)
  - Ward & Community Area: Filled with 0 (high missing percentage)
  - Location Description & Location: filled using mode imputation

2. *Data Validation*

   Invalid or out-of-scope observations were removed:
   - Coordinates falling outside official Chicago geographic boundaries
      - Latitude range: 41.6° – 42.1°
      - Longitude range: −87.9° – −87.5°
3. *Standardization*
  - IUCR codes: Standardized format
  - Text columns: Uppercase conversion, whitespace removal
  - Boolean features (Arrest, Domestic) converted to binary 0/1

This ensures compatibility with BI tools and prevents category duplication due to formatting inconsistencies.

### **Crime Severity Classification**
- Implemented FBI code-based severity mapping
- Categories: Severe and Non-severe crimes
- Based on official FBI crime classification standards

Categories assist in policy insights and hotspot detection

## Features
### **Primary Features**
- Temporal: Date, Time, Day, Month, DayOfWeek
- Spatial: Latitude, Longitude, Ward, Community Area
- Crime: Primary Type, Description, IUCR, FBI Code
- Binary: Arrest, Domestic
- Derived: Crime_Severity

## Dependencies
* python
* pandas
* numpy

## Output
- Cleaned dataset: `Chicago_Crime_Cleaned.csv`
- Ready for visualization in Power BI/Tableau

## Dashboard Preview

<img width="1441" height="815" alt="image" src="https://github.com/user-attachments/assets/5b339faf-04a1-47b4-973c-c15b83b9aa1f" />
