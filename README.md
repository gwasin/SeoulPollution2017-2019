1. Dataset Overview
Download : https://www.kaggle.com/datasets/bappekim/air-pollution-in-seoul
Content:

Hourly average measurements of six pollutants: SO₂, NO₂, CO, O₃, PM10, PM2.5.

Measurements collected across 25 monitoring stations in Seoul over the period 2017–2019.

Data is split into multiple CSV files:

Measurement_info.csv – hourly readings with instrument status.

Measurement_item_info.csv – information about pollutant codes, names, units, and quality thresholds.

Measurement_station_info.csv – metadata of monitoring stations.

Measurement_summary.csv – a condensed summary dataset 
RStudio Pubs
+1
.

2. Project Structure
├── data/
│   ├── Measurement_info.csv
│   ├── Measurement_item_info.csv
│   └── Measurement_station_info.csv
├── notebooks/
│   └── seoul_air_quality_analysis.ipynb
├── README.md
└── requirements.txt


data/: Contains raw data files sourced from Kaggle.

notebooks/: Jupyter notebook with analysis pipeline: data cleaning, visualization, modeling, and scenario simulation.

requirements.txt: Dependencies, e.g., pandas, matplotlib, seaborn, scikit-learn, tensorflow/keras.

README.md: This documentation.

3. Analysis Workflow

Data Preprocessing:

Load and merge datasets, auto-filter by instrument status (keep status = “Normal”).

Restructure from long to wide format; convert pollutants into separate columns.

Handle missing and anomalous values; apply capping (5th–95th percentile) and normalization. 
RStudio Pubs

Exploratory Data Analysis (EDA):

Compute seasonal and diurnal trends of PM2.5.

Analyze station-specific averages and identify hotspots.

Visualize weekly patterns (e.g., Sunday vs. Saturday pollution levels).

Spatial Visualization:

Create heatmaps of PM2.5 across Seoul to highlight pollution hotspots.

Machine Learning Forecasting:

Use Time Series Linear Model (TSLM) for forecasting seasonal spikes.

Train LSTM / GRU neural networks, achieving stable low error (~0.083 loss).

Scenario Simulation:

Estimate pollution outcome by simulating a 10% reduction in NO₂.

Result: Projected ~9.62% decrease in PM2.5 concentrations.

4. Key Findings

Annual PM2.5 Trends: 24.1 → 21.2 → 28.3 µg/m³ (2017–2019).

Seasonality: Winter and spring show highest levels.

Temporal Patterns: Nighttime slightly exceeds daytime; Sundays more polluted than Saturdays.

Spatial Hotspots: Central and high-traffic districts consistently exhibit higher PM2.5.

Model Performance: LSTM/GRU models effectively predict pollution peaks.

Policy Implication: Lowering NO₂ emissions could significantly reduce PM2.5 – illustrative of how data-driven modeling can guide policy.

5. Acknowledgements

Dataset: Kaggle user bappekim for the “Air Pollution in Seoul” dataset 
GitHub
Kaggle
.

Original Data Provider: Seoul Metropolitan Government’s Open Data Plaza.

Supporting Resources: Insight into data structure and preprocessing from R-based tutorials on the same dataset 
RStudio Pubs
.

6. How to Run

Clone the repository.

Install dependencies:

pip install -r requirements.txt


Place CSV files in the data/ directory.

Open and run the Jupyter notebook: analysis/seoul_air_quality_analysis.ipynb.

Explore the analysis, visualizations, and scenario modeling.

7. Contact

For questions or collaboration, feel free to reach out via my LinkedIn profile or GitHub account.
