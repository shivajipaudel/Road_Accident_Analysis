# Road_Accident_Analysis
Road Accident Analysis Dashboard using power BI

![Dashboard picture](https://github.com/shivajipaudel/Road_Accident_Analysis/assets/94693106/afb37721-b77d-4e05-8b35-f7c256a6f946)
The purpose of this Power BI dashboard is to analyze road accident data and identify patterns and trends that can help improve road safety. First step is to Import the data into Power BI and clean it to ensure it was accurate and ready for analysis. The data includes information about accidents, such as the number of vehicles involved, severity of the accident, and the location and time of the accident.

## Clients wants to create a Road Accident Dashboard for year 2021 and 2022 so that they can have insight on the below requirements
- Primary KPI - Total Casualties and Total Accident values for Current Year(CY) and YoY growth
  
- Primary KPI's — Total Casualties by Accident Severity for Current Year and YoY growth

- Secondary KPI's - Total Casualties with respect to vehicle type for Current Year

- Monthly trend showing comparison of casualties for Current Year and Previous Year (PY)

- Casualties by Road Type for Current year

- Current Year Casualties by Area/ Location & by Day/ Night

- Total Casualties and Total Accidents by Location

## Data Analysis Expressions (DAX) Formulas Used in Measures
### Total Casualties For Current Year and Year on Year Growth
(a) Current Year To Date Casualties -- CY Casualties Measure
CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])

(b) Previous Year Casualties -- PY Casualties Measure
PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))

(c) Year on Year Growth of Casualties - YoY Casualties Measure
YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]

### 2. Total Accidents for Current Year and Year on Year Growth

(a) Current Year Accidents Count -- CY Accidents Count Measure
CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])

(b) Previous Year Accidents Count -- PY Accidents Count Measure
PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))

(c) Year on Year Growth of Accidents - YoY Accidents Measure
YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]
