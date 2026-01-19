## Formula 1 Data Analytics Project
### Monaco Grand Prix 2024 — Lap-Level Driver Performance Analysis

#### Project Overview

This project analyzes lap-level timing data from the 2024 Monaco Grand Prix to evaluate driver performance, consistency, and race dynamics on one of Formula 1’s most technically demanding circuits. Using Python and the FastF1 API, I built an end-to-end analytics workflow that transforms raw motorsport telemetry into analysis-ready datasets and actionable insights.

The project is structured to mirror a real-world data analytics pipeline — from data ingestion and cleaning to exploratory analysis and BI-ready outputs.

#### Key Business & Performance Questions

Which drivers demonstrated the highest lap-time consistency at Monaco?

How do lap-time distributions change after filtering pit laps and anomalies?

Where do lap-time spikes occur, and what race events explain them?

How does Monaco’s track layout reward consistency over raw pace?

#### Analytical Approach

##### Phase 1 — Data Loading & Cleaning

Ingested official F1 lap-level timing data using the FastF1 library

Converted lap times from timedelta format to numeric seconds

Selected analysis-ready features (driver, lap number, stint, compound)

Exported clean datasets for reuse and BI tools

##### Phase 2 — Driver Performance Analysis

Analyzed lap-by-lap pace trends for top drivers

Computed summary statistics (mean lap time, standard deviation, consistency score)

Identified and filtered pit laps using time-based thresholds

Compared raw vs clean lap-time distributions using boxplots

##### Phase 3 — Driver Comparison & Ranking

Ranked drivers by pace consistency rather than outright speed

Highlighted performance stability under Monaco’s overtaking constraints

##### Phase 4 — BI-Ready Outputs

Prepared clean CSV datasets for dashboarding in Power BI / Tableau

Designed a dataset structure suitable for business and performance reporting

#### Key Insights

Monaco strongly rewards lap-time consistency due to limited overtaking opportunities

Removing pit laps significantly reduces variance and clarifies true race pace

Drivers with slightly slower average laps but tighter variance outperform inconsistent faster drivers

Distribution-based analysis reveals performance patterns hidden in averages alone

#### Tech Stack

Python

FastF1 (official Formula 1 timing data)

Pandas (data cleaning & transformation)

Matplotlib (visualization)

Jupyter Notebook

Power BI–ready CSV outputs

#### Repository Structure

formula1-driver-performance-analysis/
│
├── notebooks/
│   ├── 01_data_loading_and_cleaning.ipynb
│   ├── 02_monaco_driver_performance.ipynb
│   ├── 03_monaco_driver_comparison.ipynb
│   └── 04_monaco_driver_ranking.ipynb
│
├── data/
│   ├── raw/        # Raw lap data extracted from FastF1
│   ├── processed/ # Cleaned intermediate datasets
│   └── final/     # Analysis-ready, BI-ready CSVs
│
└── README.md

#### Future Enhancements

Extend analysis across multiple races for season-long consistency trends

Integrate weather and track-status data for contextual performance modeling

Build an interactive Power BI dashboard for executive-level insights

📎 Note: This project is intended as a portfolio demonstration of real-world data analytics workflows applied to motorsport performance data.
