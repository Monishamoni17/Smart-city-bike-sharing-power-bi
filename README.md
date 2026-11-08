# 🚲 Smart City Bike Sharing Analysis | Power BI

## 📌 Project Overview

This project focuses on analysing smart city bike-sharing data to evaluate station performance, bike availability and operational efficiency across **25 bike-sharing contracts**.

Using Microsoft Power Query and Power BI, the raw dataset was cleaned, transformed and organised into a structured star-schema data model. DAX measures were developed to calculate key performance indicators (KPIs), and interactive dashboards were created to identify operational patterns, availability gaps and areas requiring improvement.

The project follows four analytical approaches: **Descriptive, Diagnostic, Predictive and Prescriptive Analysis.**

## 🎯 Project Objectives

- Analyse bike station distribution across different contracts.
- Evaluate open and closed station performance.
- Measure bike availability and identify low-availability contracts.
- Examine station availability patterns using last-update dates.
- Identify contracts requiring station maintenance.
- Develop data-driven strategies to improve bike availability and operational efficiency.

## 📂 Dataset Information

| Attribute | Details |
|---|---|
| Dataset | Bike Station Sharing Data |
| File format | CSV |
| Source | Module-End Assignment Dataset |
| Total Stations | 2,856 |
| Total Contracts | 25 |
| Data Timeline | January 2022 – November 2025 |
| Domain | Smart city public bike sharing |

**Key attributes:**
- Station Name and Station ID
- Address, Latitude and Longitude
- Contract Name
- Station Status (Open / Closed)
- Bike Stands
- Available Bikes
- Available Bike Stands
- Last Update

## 🛠️ Tools & Technologies

| Tool | Application |
|---|---|
| Microsoft Power BI Desktop | Data modelling and dashboard development |
| Power Query Editor | Data cleaning and transformation |
| DAX | KPI calculations and analytical measures |
| Excel | Dataset inspection and validation |
| GitHub | Project documentation and portfolio presentation |

## 🔄 Data Cleaning & Transformation

The raw CSV dataset was processed using Power Query Editor.

**Key transformation steps:**

1. Imported the raw CSV dataset into Power Query.
2. Performed data profiling using Column Quality, Column Distribution and Column Profile.
3. Corrected data types for text, whole number, decimal and date columns.
4. Split the Last Update column into Date and Time.
5. Removed unnecessary columns.
6. Created unique dimension tables and identifiers.
7. Developed a central fact table containing foreign keys and numerical attributes.
8. Created a Date dimension for date-based analysis.
9. Checked and validated the transformed data.

## 🏗️ Data Modelling

A **Star Schema** was developed to organise the data efficiently and support analytical reporting.

### Data Model Structure

**Fact Table:**
- Bike_availability_fact

**Dimension Tables:**
- Station_dim
- Contract_dim
- Status_dim
- Date_dim

**Relationships:**
- Station_dim → Bike_availability_fact
- Contract_dim → Bike_availability_fact
- Status_dim → Bike_availability_fact
- Date_dim → Bike_availability_fact

All relationships follow a one-to-many structure from the dimension tables to the fact table, with single-direction filtering.

## 📐 Key DAX Measures & KPIs

| KPI | Result |
|---|---:|
| Total Stations | 2,856 |
| Total Contracts | 25 |
| Total Bike Stands | 57.20K |
| Total Available Bikes | 19.65K |
| Total Available Bike Stands | 32.12K |
| Open Stations | 2.65K |
| Closed Stations | 206 |
| Open Station % | 92.79% |
| Closed Station % | 7.21% |
| Bike Availability % | 34.34% |
| Average Bikes per Station | 6.88 |
| Average Stands per Station | 20.03 |

### Sample DAX Calculations

**1. Total Stations**
```dax
Total Stations =
DISTINCTCOUNT(Bike_availability_fact[Station ID])
```

**2. Open Stations**
```dax
Open Stations =
CALCULATE(
    [Total Stations],
    Status_dim[Status] = "OPEN"
)
```

**3. Closed Station Percentage**
```dax
Closed Station % =
DIVIDE(
    [Closed Stations],
    [Total Stations]
)
```

**4. Bike Availability Percentage**
```dax
Bike Availability % =
DIVIDE(
    [Total Available Bikes],
    [Total Bike Stands]
)
```

## 📊 Power BI Dashboard Visualizations

The Power BI report consists of five interactive pages.

### 1. KPI Summary
Provides an overview of the entire bike-sharing network through key performance indicators, including total stations, open and closed stations, bike availability and station capacity.

### 2. Descriptive Analysis
Explores the distribution of bike stations across contracts, identifies the largest bike-sharing networks and visualises geographical station locations.

### 3. Diagnostic Analysis
Examines the relationship between network size and station closures, identifies contracts with low bike availability and highlights major contributors to station closures.

### 4. Predictive Analysis
Uses monthly line charts and trend lines to examine patterns in average bikes per station and closed stations based on their last-update dates.

### 5. Prescriptive Analysis
Identifies contracts requiring improved bike availability and prioritises station maintenance based on closure rates and the number of closed stations.

## 🔍 Key Business Insights

| Analysis Area | Key Finding |
|---|---|
| Network Distribution | Top 10 contracts account for approximately 84% of all stations. |
| Station Performance | 92.79% of stations are open. |
| Bike Availability | Only 34.34% of total bike stands hold available bikes. |
| Station Closures | Five contracts contribute approximately 79% of all closed stations. |
| Low Availability | Vilnius, Rouen, Mulhouse, Marseille, Cergy-Pontoise and Santander have fewer than 0.5 average bikes per station. |
| Maintenance Priority | Vilnius has the highest closed-station percentage at 97.30%. |

### 💡 Major Findings

- Lyon has the highest number of stations (448), followed by Toulouse (431).
- Marseille has the highest number of closed stations (52).
- Vilnius has the highest proportion of closed stations (97.30%).
- Lund, Dublin and Bruxelles-Capitale have comparatively higher average bike availability.
- Bike availability and station closures show fluctuating monthly patterns.

## 💡 Bike Sharing Network Improvement Strategies

1. **Bike Redistribution:** Improve bike distribution within individual contracts based on station-level availability, using high-availability contracts as performance benchmarks.
2. **Station Maintenance:** Prioritise repairing and reopening stations in contracts with high closure percentages.
3. **Performance Monitoring:** Monitor closed-station percentages monthly and establish alerts when the closure rate exceeds 10%.
4. **Future Analysis:** Incorporate revenue, distance and operating cost data to analyse revenue per kilometre and operational cost efficiency.

## ⚠️ Data Limitations

- The dataset contains the last-update date for each station rather than continuous historical observations.
- Therefore, monthly trend lines represent the distribution of station records by their last-update dates and should not be interpreted as reliable forecasts of future performance.
- The difference between total bike stands and the combined available bikes and available stands should be validated against the original source data.
- Operational reasons for station closures cannot be established from the available attributes alone.

## 🏁 Conclusion

This project demonstrates the application of Power Query, data modelling and DAX in transforming raw bike-sharing data into meaningful analytical insights. The interactive Power BI dashboards help identify station performance issues, bike availability gaps and maintenance priorities across different contracts.

The findings highlight the importance of effective bike distribution, timely station maintenance and continuous performance monitoring in improving the efficiency of smart city bike-sharing networks.

## 📁 Repository Structure

```text
smart-city-bike-sharing-power-bi/
│
├── Dataset/
│   └── bike-stations-sharing-data.csv
│
├── PowerBI/
│   └── Smart_City_Bike_Sharing_Analysis.pbix
│
├── Dashboard_Screenshots/
│   ├── KPI_Summary.png
│   ├── Descriptive_Analysis.png
│   ├── Diagnostic_Analysis.png
│   ├── Predictive_Analysis.png
│   └── Prescriptive_Analysis.png
│
├── Documentation/
│   └── Project_Report.pdf
│
└── README.md
```

*Note: This is a suggested folder structure. Include the dataset only if its sharing and usage terms permit redistribution.*

## 🚀 How to Explore the Project

1. Clone or download this repository.
2. Open the `.pbix` file using Microsoft Power BI Desktop.
3. Explore the five dashboard pages.
4. Interact with the slicers to analyse different contracts, years, months and station statuses.
5. Review the project documentation for detailed methodology and findings.

## 👩‍💻 About the Author

**Monisha B**

Aspiring Data Analyst | Power BI | Excel | SQL | Data Visualization

Interested in transforming raw data into meaningful insights and supporting better business decisions through data analytics.

---

⭐ If you find this project interesting, feel free to explore the dashboards and share your feedback!
