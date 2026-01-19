## Power BI Dashboard Design (Mac-Compatible)

Power BI Desktop is not available natively on macOS. To keep this project reproducible and portfolio-ready, I exported Power BI–ready datasets and documented the dashboard layout and DAX measure mapping. The dashboard can be recreated directly in Power BI Desktop using the CSV files in `data/final/`.

### Dashboard Title
**Monaco GP 2024 — Driver Pace & Consistency Analysis**

### Data Sources
- `data/final/monaco_2024_clean_laps.csv` (lap-level race pace data, pit laps removed)
- `data/final/monaco_2024_driver_summary.csv` (driver-level metrics: mean pace + consistency)

---

### Page 1: Executive Overview
**Goal:** Quick summary of who was fastest and who was most consistent.

**Visuals:**
- KPI Card: Fastest Average Lap Time
- KPI Card: Most Consistent Driver (lowest consistency score)
- KPI Card: Total Clean Laps
- Table: Driver | Mean Lap Time | Consistency Score | Lap Count

---

### Page 2: Driver Comparison
**Goal:** Compare drivers on pace vs consistency.

**Visuals:**
- Bar Chart: Mean Lap Time by Driver (ascending)
- Bar Chart: Consistency Score by Driver (ascending)
- Scatter Plot: Mean Lap Time vs Consistency Score

---

### Page 3: Lap Time Distribution
**Goal:** Show lap-to-lap variability after cleaning.

**Visuals:**
- Box Plot (or strip plot): LapTimeSeconds by Driver
- Line Chart: LapNumber vs LapTimeSeconds (per driver)

📊 **Driver Consistency Comparison**  
See `/exports/monaco_driver_consistency.png`


**Filters:**
- Driver slicer
- Lap number range slicer

### Data Pipeline Overview
This project follows a structured, reproducible data pipeline designed to mirror real-world analytics workflows. Raw lap-level timing data is extracted from the FastF1 API and stored without modification to preserve data integrity. The data is then cleaned and standardized (removal of missing lap times, conversion to seconds, and filtering of pit laps) before being used for exploratory analysis and driver performance comparisons. Final aggregated metrics—including average lap time, variance, and consistency scores—are exported as analysis-ready datasets for downstream visualization and dashboarding. This staged pipeline ensures transparency, traceability, and reusability across notebooks and tools such as Power BI.