# EDA_NYC_Taxi_Analysis
 Analyze patterns in the data that can inform strategic decisions to improve service efficiency, maximize revenue, and enhance passenger experience.
# 🚖 NYC Yellow Taxi Data Analysis (2023)

## 📌 Project Overview
This project performs an **Exploratory Data Analysis (EDA)** on the **New York City Yellow Taxi Trip Records (2023)** dataset.  
The objective is to uncover **patterns in demand, revenue, fares, and customer behavior** to provide actionable recommendations that can:

- Improve **service efficiency**  
- Maximize **revenue**  
- Enhance **passenger experience**  

The repository contains:
- A **Python script** with complete data processing and analysis pipeline.  
- A **presentation** summarizing findings, visualizations, and strategic recommendations.  

---

## 📂 Repository Structure

├── EDA_Assg_NYC_Taxi_Starter.py # Python script for data cleaning, EDA & visualization
├── EDA_NYC_Taxi_Analysis_ChaitraNingaraja.pptx # Presentation with summarized insights & recommendations
├── README.md # Project documentation


---

## 📊 Dataset

- **Source**: [NYC Taxi & Limousine Commission (TLC)](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)  
- **Format**: Parquet (`*.parquet`)  
- **Scope**: January–December 2023 (12 monthly files)  
- **Fields include**:
  - `tpep_pickup_datetime`, `tpep_dropoff_datetime`
  - `Passenger_count`, `Trip_distance`
  - `Fare_amount`, `Tip_amount`, `Total_amount`, `Tolls_amount`
  - `Payment_type`, `RateCodeID`
  - `PULocationID`, `DOLocationID` (pickup & dropoff zones)

---

## ⚙️ Approach

1. **Data Loading & Sampling**  
   - Loaded monthly parquet files.  
   - Applied **5% stratified hourly sampling** to manage memory efficiently.

2. **Data Cleaning & Preprocessing**  
   - Fixed invalid/negative values.  
   - Handled missing values (e.g., `RateCodeID`, `passenger_count`).  
   - Combined duplicate columns (e.g., `Airport_fee`).  
   - Removed unrealistic trips & outliers.  

3. **Exploratory Analysis**  
   - **Temporal trends** (hourly, daily, monthly demand).  
   - **Financial insights** (revenue patterns, fare vs. distance).  
   - **Passenger behavior** (group sizes, tipping).  
   - **Geospatial insights** (hotspots by pickup/dropoff zones).  

4. **Visualization**  
   - Histograms, scatter plots, bar plots.  
   - Correlation heatmaps.  
   - Geo-spatial maps of NYC taxi zones using **GeoPandas**.

5. **Insights & Recommendations**  
   - Peak demand hours, zones, seasonal variation.  
   - Strategies for routing, pricing, and fleet positioning.  

---

## 📈 Key Insights

- **Demand Patterns**
  - Peak: **5–7 PM**, lowest: **2–5 AM**.
  - **Midweek (Tue–Wed)** highest demand; **Sun–Mon** lowest.  
  - Seasonal highs in **May & October**; lows in **Feb & Sept**.  

- **Revenue**
  - Q2 & Q4 generate maximum revenue.  
  - Long trips inflate average fares due to outliers.  

- **Fare Drivers**
  - Strong correlation with **trip distance**.  
  - Weak correlation with **trip duration** (traffic causes variability).  
  - Passenger count has **negligible effect** on fare.  

- **Customer Behavior**
  - Tips rise with **distance**; solo riders tip highest.  
  - Digital payments dominate (credit card > cash).  

- **Operational Hotspots**
  - Busiest zones: **JFK, LaGuardia, Midtown, Penn Station, Times Square**.  
  - Staten Island zones show negligible demand.  

---

## 💡 Recommendations

1. **Routing & Dispatch**
   - Add cabs during **5–7 PM** peaks.  
   - Reduce fleet during **2–5 AM**; keep some at airports.  
   - Prioritize **Tue–Wed** business zones, **Sun–Mon** maintenance.  

2. **Cab Positioning**
   - Evenings: Midtown, Penn Station, Times Square.  
   - Late nights: Airports (flight schedules).  
   - Seasonal: Pre-plan for **May & Oct** demand spikes.  

3. **Pricing Strategy**
   - Surge pricing in **peak hours**.  
   - Flat competitive fares for **airport trips**.  
   - Discounts during **low-demand hours**.  
   - Incentives for **long trips**.  

---

## 🛠️ Requirements

The project uses **Python 3.10+** with the following libraries:

```bash
numpy==1.26.4
pandas==2.2.2
matplotlib==3.10.0
seaborn==0.13.2
geopandas
