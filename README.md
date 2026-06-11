# Solar Power Plant Performance & Fault Detection Analysis

## Project Overview
This project analyzes the thermodynamic and electrical performance of a utility-scale solar power generation facility. Using Python and Pandas, I ingested and processed over 36,000 rows of generation and weather sensor data to create a digital twin of the plant. The primary objective was to track inverter efficiency, correlate environmental factors with power output, and isolate hardware failures within the equipment fleet.

## Tech Stack & Tools
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib
* **Environment:** Jupyter Notebook

## Dataset
The dataset utilized is the Solar Power Generation Data from Kaggle, containing two primary tables for Plant 1:
1. **Power Generation Data:** 15-minute interval readings of DC Power, AC Power, and Daily Yield across 22 individual inverters.
2. **Weather Sensor Data:** Environmental metrics including Ambient Temperature, Module Temperature, and Solar Irradiation.

## Key Methodologies & Findings

### 1. Data Engineering & Alignment
* Re-scaled AC/DC power metrics to resolve sensor-calibration unit mismatches.
* Unified mismatched chronological data formats, establishing a robust datetime index.
* Successfully merged local inverter power generation logs with site-wide weather sensor telemetry using precise temporal and spatial keys.

### 2. Environmental Impact Verification
* Plotted daily DC Power generation curves and identified erratic mid-day power drops.
* Utilized dual-axis visualization to overlay solar irradiation data onto the power generation curve, definitively proving that localized power drops were directly correlated with passing cloud cover rather than equipment instability.

### 3. Root Cause Analysis & Anomaly Detection
* Aggregated 34 days of operational data to calculate the total DC power yield for all 22 inverters.
* **Hardware Fault Isolated:** Identified two specific inverters operating at a 10% to 15% capacity deficit compared to the fleet baseline.
* **Diagnostic Conclusion:** By performing a time-series comparison against a healthy baseline inverter, I determined the failing machines were experiencing *Capacity Loss* rather than *Availability Loss*. The daily power curves remained stable but depressed, indicating severe localized panel soiling, shading, or blown string fuses, requiring immediate physical maintenance.

## Business Impact
This analysis translates raw digital telemetry into actionable maintenance intelligence, allowing for targeted physical repairs that prevent long-term revenue loss from degraded equipment.
