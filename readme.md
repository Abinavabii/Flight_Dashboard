# ✈️ Flight Performance & Delay Analysis Dashboard  
### Power BI Business Intelligence Project

---

<p align="center">
  <img src="./flight_banner.png" alt="Flight Dashboard Banner" width="100%"/>
</p>

---
## 📌 Project Overview 

This project analyzes 327,000+ U.S. flight records to evaluate airline operational performance, delay patterns, and airport efficiency using Power BI.

The goal was to transform raw flight data into an interactive, executive-level dashboard that provides actionable insights into flight delays and operational reliability.

---

## 🎯 Business Objectives

The dashboard was designed to:

- Measure on-time performance  
- Identify high-delay routes and carriers  
- Detect seasonal and hourly delay trends  
- Compare airline and airport efficiency  
- Support operational decision-making  

---

## 📊 Dataset Information

- 327K+ flight records  
- Key fields:
  - Arrival Delay
  - Departure Delay
  - Carrier
  - Origin Airport
  - Destination Airport
  - Air Time
  - Distance
  - Month & Hour

---

## 🧹 Data Preparation

Performed in Power Query:

- Removed null arrival delay records  
- Adjusted data types  
- Cleaned and structured dataset  
- Created calculated columns for categorization  

---

## 🧠 Data Modeling & DAX

### 🔹 Calculated Columns

#### Delay Category

```DAX
Delay Category =
SWITCH(
    TRUE(),
    flights[arr_delay] <= 0, "On Time",
    flights[arr_delay] <= 15, "Minor Delay",
    flights[arr_delay] <= 60, "Moderate Delay",
    "Severe Delay"
)
```

Used to classify delay severity for advanced analysis.

---

#### On Time Flag

```DAX
On Time Flag = IF(flights[arr_delay] <= 0, "On Time", "Delayed")
```

Used for binary performance segmentation.

---

### 🔹 Measures

#### Total Flights

```DAX
Total Flights = COUNTROWS(flights)
```

---

#### Average Arrival Delay

```DAX
Avg Arrival Delay = AVERAGE(flights[arr_delay])
```

---

#### Average Departure Delay

```DAX
Avg Departure Delay = AVERAGE(flights[dep_delay])
```

---

#### On-Time Percentage

```DAX
On Time % =
DIVIDE(
    CALCULATE(COUNTROWS(flights), flights[arr_delay] <= 0),
    COUNTROWS(flights)
)
```

Demonstrates dynamic filter context and KPI calculation.

---

## 📈 Dashboard Components

### 1️⃣ Executive KPI Section
- Total Flights
- Avg Arrival Delay
- Avg Departure Delay
- On-Time %
- Total Delay Minutes

Provides quick operational snapshot.

---

### 2️⃣ Monthly Trend Analysis
Line chart showing seasonal delay fluctuations.

---

### 3️⃣ Delay Distribution
- Donut Chart → Delay severity breakdown  
- Pie Chart → On-Time vs Delayed  

---

### 4️⃣ Airline Performance Analysis
- Average delay by carrier  
- Flight volume comparison  
- Matrix (Carrier vs Airport) with conditional formatting  

---

### 5️⃣ Airport Performance Comparison
Comparison of:
- JFK
- LGA
- EWR

Identifies congestion and inefficiencies.

---

### 6️⃣ Interactive Features
- Slicers (Month, Origin, Delay Category)
- Drill-down capability
- Conditional formatting (heatmap style)
- Dynamic KPI recalculation

---

## 📊 Key Insights

- 59% of flights operate on time  
- Moderate delays represent the majority of delay cases  
- Certain airlines consistently show higher average delays  
- Seasonal delay spikes observed mid-year  
- Evening flights experience higher delay rates  

---

## 💼 Skills Demonstrated

- Data Cleaning & Transformation  
- Data Modeling  
- DAX (Measures & Calculated Columns)  
- KPI Design  
- Conditional Formatting  
- Multi-Dimensional Analysis  
- Dashboard Storytelling  
- Business Intelligence Thinking  

---

## 📬 Connect With Me

I am open to opportunities in:

- Data Analytics
- Business Intelligence
- Power BI Development

Feel free to connect or provide feedback!
