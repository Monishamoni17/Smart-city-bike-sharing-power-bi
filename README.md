# 🚲 Smart City Bike Sharing Analysis | Power Query & Power BI

## 📌 Project Overview

This project focuses on analysing public bike-sharing data to understand station performance, bike availability, operational status and distribution patterns across different bike-sharing contracts.

Using **Microsoft Power BI and Power Query**, I transformed raw bike station data into meaningful business insights through data cleaning, data transformation, data modelling, DAX calculations and interactive dashboard development.

The project applies the four major types of business analytics: **Descriptive, Diagnostic, Predictive and Prescriptive Analysis** to identify operational challenges and suggest improvements for bike-sharing networks.

## 🎯 Project Objectives

- Analyse bike station distribution across different contracts.
- Understand bike availability and station capacity.
- Identify open and closed station patterns.
- Compare bike availability across contracts.
- Examine monthly patterns in bike availability and station closures.
- Identify contracts requiring additional bikes and station maintenance.
- Provide data-driven recommendations to improve operational efficiency.

## 📂 Dataset Information

| Description | Details |
|---|---|
| Dataset | Bike Stations Sharing Data |
| Source | Module-End Assignment Dataset |
| Domain | Smart City / Urban Mobility |
| Data Period | January 2022 – November 2025 |
| Total Records | 2,856 stations |
| Total Contracts | 25 |
| Data Format | CSV |

The dataset contains information about bike stations, station locations, contracts, operational status, total bike stands, available bikes, available bike stands and last-update timestamps.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Excel | Initial data inspection and validation |
| Power Query | Data cleaning and transformation |
| Power BI | Data modelling, DAX calculations and interactive dashboards |
| DAX | Calculated measures and KPI development |
| GitHub | Project documentation and portfolio presentation |

## 🔄 Project Workflow

### 1. Data Cleaning and Preparation

- Imported the raw CSV dataset into Power BI.
- Inspected data using column quality, column distribution and column profiling.
- Checked and corrected data types.
- Identified and handled duplicate and unwanted records where applicable.
- Removed unnecessary columns.
- Split the Last Update column into separate Date and Time columns.
- Prepared the dataset for further analysis.

### 2. Data Transformation – Power Query

- Used Power Query Editor to clean and transform the dataset.
- Created separate fact and dimension tables.
- Extracted relevant attributes for dimension tables.
- Prepared station, contract and status information.
- Created a Date Dimension table containing Year, Month, Month Name and Year Month.
- Validated the transformed data.

### 3. Data Modelling – Power BI

Created a **Star Schema** consisting of one central fact table and four dimension tables.

| Table | Purpose |
|---|---|
| Bike_availability_fact | Stores station-level bike availability and capacity information |
| Station_dim | Station ID, station name, address, latitude and longitude |
| Contract_dim | Contract ID and contract name |
| Status_dim | Status ID and station status |
| Date_dim | Date, year, month, month name and year month |

Established one-to-many relationships between the dimension tables and the central fact table, using single-direction filtering.

### 4. DAX Calculations

Created DAX measures to calculate important business KPIs and support dashboard analysis.

**Key measures:**
- Total Stations
- Total Contracts
- Total Bike Stands
- Total Available Bikes
- Total Available Bike Stands
- Open Stations
- Closed Stations
- Open Station Percentage
- Closed Station Percentage
- Bike Availability Percentage
- Average Bikes per Station
- Average Stands per Station

### 5. Dashboard Development

Developed five interactive Power BI report pages to provide different perspectives of bike-sharing network performance.

**Report pages include:**

1. KPI Summary
2. Descriptive Analysis
3. Diagnostic Analysis
4. Predictive Analysis
5. Prescriptive Analysis

**Key visualisations:**
- KPI cards for station count, bike availability and operational status.
- Contract-wise station distribution using column charts.
- Top 10 contracts by station count using a funnel chart.
- Geographical distribution of stations using a map.
- Open vs Closed stations using a donut chart.
- Stations vs Closed Stations using a scatter chart.
- Average Bikes per Station by Contract using a bar chart.
- Closed Stations by Contract using a waterfall chart.
- Monthly bike availability and closed-station trends using line charts.
- Contracts requiring more bikes and station repairs using tables with conditional formatting.

**Interactivity:**
- Contract Name slicer.
- Year slicer.
- Month slicer.
- Status slicer.
- Cross-filtering between visuals.
- Top 10 filtering.
- Conditional formatting.

## 📊 Four Types of Business Analysis

### 1. Descriptive Analysis – What Happened?

- The dataset contains **2,856 bike stations** across 25 contracts.
- The network has approximately **57.20K total bike stands**.
- Total available bikes are approximately **19.65K**.
- 92.79% of stations are open, while 7.21% are closed.
- The top 10 contracts account for approximately 84% of all stations.
- Lyon (448), Toulouse (431) and Bruxelles-Capitale (357) have the highest station counts.
- Overall bike availability is 34.34%.

### 2. Diagnostic Analysis – Why Did It Happen?

- Marseille recorded the highest number of closed stations, with 52.
- Vilnius recorded the highest station closure percentage at 97.30%.
- Cergy-Pontoise recorded a closure percentage of 69.57%.
- Six contracts—Vilnius, Rouen, Mulhouse, Marseille, Cergy-Pontoise and Santander—have particularly low average bikes per station.
- Lund, Dublin, Bruxelles-Capitale and Ljubljana recorded higher average bikes per station.

### 3. Predictive Analysis – What Is Likely to Happen?

- The monthly average bikes-per-station visual shows a slightly rising pattern.
- The monthly closed-station trend shows a slightly downward pattern with occasional spikes.
- These patterns help identify possible operational trends that require monitoring.
- Reliable future forecasting is limited because the dataset contains only one last-update record per station rather than repeated historical snapshots.

### 4. Prescriptive Analysis – What Should Be Done?

Based on the findings, the following improvement strategies were identified:

- **Bike Redistribution:** Redistribute bikes within individual contracts, giving priority to low-availability contracts after addressing station maintenance issues.
- **Station Maintenance:** Prioritise repair and reopening of stations in contracts with high closure percentages, including Vilnius, Cergy-Pontoise, Santander, Rouen, Lillestrom and Mulhouse.
- **Performance Monitoring:** Monitor station closure percentages regularly and establish an operational alert when the closure rate exceeds 10%.
- **Future Data Analysis:** Include additional information such as revenue, distance travelled and operating costs to evaluate financial and operational efficiency.

## 💡 Key Business Insights

| Area | Key Finding |
|---|---|
| Total Stations | 2,856 |
| Total Contracts | 25 |
| Total Bike Stands | 57.20K |
| Total Available Bikes | 19.65K |
| Open Station Percentage | 92.79% |
| Closed Stations | 206 |
| Closed Station Percentage | 7.21% |
| Bike Availability | 34.34% |
| Highest Station Count | Lyon – 448 |
| Highest Closed Station Count | Marseille – 52 |
| Highest Closure Percentage | Vilnius – 97.30% |
| Highest Average Bikes per Station | Lund – 12.7 |

## 📈 Business Value

This project demonstrates how data analytics can help bike-sharing operators:

- Monitor station performance and bike availability.
- Identify contracts with operational challenges.
- Understand station distribution across different locations.
- Identify stations requiring maintenance.
- Improve bike redistribution within individual contracts.
- Monitor operational performance using interactive dashboards.
- Support better decisions through data-driven insights.

## ⚠️ Data Limitations & Validation

- The dataset contains one last-update record per station, rather than repeated historical snapshots. Therefore, monthly trends should not be treated as reliable historical forecasting.
- Total Bike Stands (57.20K) does not equal Total Available Bikes (19.65K) plus Total Available Bike Stands (32.12K). The difference of approximately 5.43K requires validation against the original dataset.
- The dataset does not contain revenue, distance travelled or operating cost information, limiting financial and demand analysis.

## 📁 Project Files

The repository can be organised as follows:

```text
Smart-City-Bike-Sharing-Power-BI/
│
├── Dataset/
│   └── bike-stations-sharing-data.csv
│
├── PowerBI/
│   └── Smart_City_Bike_Sharing_Analysis.pbix
│
├── Documentation/
│   └── Smart_City_Bike_Sharing_Project_Report.pdf
│
├── Screenshots/
│   ├── KPI_Summary.png
│   ├── Descriptive_Analysis.png
│   ├── Diagnostic_Analysis.png
│   ├── Predictive_Analysis.png
│   └── Prescriptive_Analysis.png
│
└── README.md
```

*Replace the example filenames with the actual filenames uploaded. Share the dataset only if redistribution is permitted.*

## 🚀 Skills Demonstrated

- Data Cleaning and Data Preparation
- Exploratory Data Analysis
- Power Query and Data Transformation
- Star Schema and Data Modelling
- DAX Measures and KPI Development
- Data Visualization
- Descriptive and Diagnostic Analysis
- Predictive and Prescriptive Analysis
- Power BI Dashboard Development
- Business Insights and Data-Driven Recommendations

## 👩‍💻 About Me

I am an **Aspiring Data Analyst** interested in transforming raw data into meaningful insights and supporting better business decisions.

This project represents my practical learning in Power Query, data modelling, DAX and Power BI, with a focus on business-oriented data analysis and interactive visualisation.

**Thank you for visiting my project!**
