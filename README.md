# ⚡ Fleet Battery Performance Analytics

## Overview
This project presents a comprehensive **data warehousing and analytics solution** for monitoring and improving electric vehicle (EV) fleet performance.  
By integrating telemetry data, maintenance logs, and technician records, it provides insights into **battery degradation patterns**, **failure hotspots**, and **maintenance effectiveness**.  
The project uses a **star schema** architecture, **OLAP queries**, and **interactive dashboards** to enable data-driven decision-making for predictive fleet maintenance.

---

## Objectives
- Design and implement a scalable **data warehouse** for EV fleet data.  
- Analyze **battery performance** and **failure trends** across time, location, and environmental factors.  
- Evaluate the impact of **technician expertise** on maintenance outcomes.  
- Build **OLAP queries and dashboards** to uncover actionable insights for fleet optimization.  

---

## Data Sources
The analysis combines data from multiple domains to form a unified decision-support framework.

| Dataset | Description |
|----------|--------------|
| **Telemetry_Data.csv** | Real-time data from EV sensors (battery level, mileage, engine temperature, driving conditions). |
| **Maintenance_Logs.csv** | Records of service, repairs, and component replacements linked to performance issues. |
| **Technician_Info.csv** | Technician IDs, specialization, and certification details to evaluate maintenance impact. |

---

## Data Modeling (Star Schema)
The data warehouse uses a **star schema** with one central fact table and four supporting dimension tables.

### **Fact Table**
**FACT_BATTERY_USAGE_FINAL**  
Captures performance metrics such as battery charge, engine temperature, and failure indicators.

| Column | Description |
|---------|--------------|
| VEHICLE_ID | Unique vehicle identifier |
| DATE_ID | Time dimension reference |
| LOCATION_NAME | Region or operating environment |
| TECHNICIAN_ID | Assigned maintenance technician |
| BATTERY_LEVEL | Remaining battery charge |
| ENGINE_TEMP | Engine temperature (°C) |
| FAILURE_FLAG | Binary indicator for failure events |

### **Dimension Tables**
- **DIM_DATE_FINAL:** Date hierarchy (day, month, quarter, year)  
- **DIM_LOCATION_FINAL:** Regional and environmental details (temperature, humidity)  
- **DIM_TECHNICIAN_FINAL:** Technician information and skill levels  
- **DIM_VEHICLE_FINAL:** Vehicle specifications (make, model, type)

This structure supports **OLAP operations** like slicing, dicing, roll-up, and drill-down to uncover multi-dimensional insights.

---

## OLAP Queries & Insights

### 1. **Average Battery Level by Region**
Identifies geographic regions where battery performance is weakest.  
> ✅ West region shows highest efficiency; South region exhibits lower averages, suggesting maintenance or climate-related factors.

### 2. **Failure Rate Analysis**
Highlights regional failure concentration for targeted maintenance planning.  
> ⚠️ South and East regions show the highest failure percentages, making them top candidates for preventive intervention.

### 3. **Environmental Correlation**
Explores the relationship between **humidity** and **failure rate**.  
> 💡 Humidity contributes to battery degradation; dry regions maintain better performance consistency.

### 4. **Technician Performance Impact**
Evaluates technician certifications and post-repair outcomes.  
> 👷‍♂️ Level 2+ technicians have the lowest repeat failure rates, demonstrating measurable value in upskilling programs.

### 5. **Battery Drop Detection (Time-Series)**
Uses `LAG()` to detect sudden battery drops and identify high-risk vehicles early.

---

## Visual Reporting (Tableau)
Developed interactive dashboards to support executive-level insights and storytelling.

| Dashboard | Description |
|------------|--------------|
| **Battery Level Over Time** | Tracks battery performance trends for predictive maintenance. |
| **Regional Failure Hotspots** | Visualizes geographic regions with high failure frequency. |
| **Technician Effectiveness** | Compares post-maintenance performance by certification. |
| **Maintenance Cost vs Failures** | Analyzes preventive spending and ROI on reduced failures. |
| **Top Risk Vehicles** | Highlights vehicles most prone to battery degradation. |

---

## Key Results
- 🌡️ **High temperature and humidity** correlate strongly with elevated failure rates.  
- ⚙️ **Preventive maintenance** spending reduces failure rates significantly.  
- 👷‍♀️ **Certified technicians** deliver more reliable repairs and lower post-maintenance failures.  
- 📊 **Tableau dashboards** transformed analytical results into actionable fleet management insights.  

---

## Future Enhancements
- Integrate **real-time IoT sensor feeds** for live fleet monitoring.  
- Incorporate **machine learning models** for predictive maintenance.  
- Expand analytics beyond batteries to include **motor and controller performance**.  
- Conduct **ROI analysis** for technician training and certification programs.  

---

## ⚖️ License
This project is licensed under the [MIT License](LICENSE).

---

## 👩‍💻 Author
**Pria Khatik**  
M.S. in Artificial Intelligence & Business Analytics  
University of South Florida  

🔗 [LinkedIn – Pria Khatik](https://www.linkedin.com/in/priyakhatik/)  
📅 *2025 | Data Warehousing & Fleet Analytics Project*
