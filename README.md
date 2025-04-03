# Electricity Consumption Analysis

This project provides an integrated workflow for analyzing electricity demand, pricing, and weather data over multiple years. The goal is to clean and preprocess the data, perform exploratory data analysis (EDA), and build forecasting models using Random Forest and XGBoost.

## Table of Contents

1. [Overview](#overview)
2. [Data Sources](#data-sources)
3. [Project Structure](#project-structure)
4. [How to Run](#how-to-run)
5. [Results and Conclusions](#results-and-conclusions)
6. [Next Steps](#next-steps)

## Overview

This notebook integrates multiple datasets:
- Historic electricity demand data (2009-2024)
- Yearly electricity demand data for 2009
- 2023 electricity prices (ONS data)
- London weather data for 2023

We perform the following steps:
- **Data Loading and Cleaning:** Import datasets, standardize columns, convert date formats, handle missing values, and clean data.
- **Data Preprocessing and Feature Engineering:** Extract time-based features, create rolling averages, and engineer additional features (e.g., peak/off-peak indicators).
- **Exploratory Data Analysis (EDA):** Visualize trends, seasonal effects, and relationships among energy demand, prices, and weather factors.
- **Model Building and Forecasting:** Build and evaluate forecasting models (Random Forest and XGBoost) using error metrics such as MAE and RMSE.
- **Conclusions:** Summarize the insights from the analysis and discuss model performance.

## Data Sources

- **Historic Electricity Demand:** `historic_demand_2009_2024.csv` and `historic_demand_year_2009.csv`
- **Electricity Prices:** `electricitypricesdataset211223.xlsx` (ONS data)
- **Weather Data:** `london0_23_weather_data.csv`
- **Merged Output for 2023:** The processed output is saved as `energy_weather_electricity_2023.csv` after merging demand, price, and weather data.

## Project Structure

- **Electricity_Consumption_Integrated.ipynb** # The main Jupyter Notebook with the full analysis
- **Datasets** 
    - **historic_demand_2009_2024.csv** # Historic electricity demand data (2009-2024) 
    - **historic_demand_year_2009.csv** # Yearly electricity demand data for 2009 
    - **electricitypricesdataset211223.xlsx** # Electricity prices from ONS 
    - **london0_23_weather_data.csv** # London weather data for 2023 
    - **energy_weather_electricity_2023.csv** # Merged dataset output for 2023 (created during processing) 
- **README.md** # This README file


## How to Run

1. **Clone the Repository:**  
   Ensure all the required files are in the same directory.
   
2. **Install Dependencies:**  
   You may need to install the following Python packages:
   - pandas
   - matplotlib
   - seaborn
   - openpyxl (for reading Excel files)
   - scikit-learn
   - xgboost
   - IPython
   
   You can install them using pip:
   ```bash
   pip install pandas matplotlib seaborn openpyxl scikit-learn xgboost ipython
   ```

3. **Open the Notebook:**
   Launch Jupyter Notebook and open Electricity_Consumption_Integrated.ipynb.

4. **Run All Cells:**
   Execute the notebook sequentially to perform data loading, cleaning, analysis, and modeling.

## Results and Conclusions

The forecasting models indicate that energy demand trends are fairly predictable:

**Random Forest:** MAE ≈ 343, RMSE ≈ 475

**XGBoost:** MAE ≈ 367, RMSE ≈ 480

These results suggest that, on average, the Random Forest model's predictions are within ±343 units of the actual energy consumption. For example, if the model forecasts a demand of 5,000 units, actual demand is likely to be between approximately 4,657 and 5,343 units. This level of accuracy supports effective planning, though operators should account for occasional larger deviations (up to around 475 units). The analysis confirms that while the current models capture key consumption patterns, there is room for further improvement.

## Next Steps

- **Feature Enhancement:** Explore additional features (e.g., more granular weather data, economic indicators).

- **Model Tuning:** Further refine model parameters and consider ensemble methods.

- **Real-Time Integration:** Develop a dashboard to integrate real-time data for continuous forecasting.

- **Extended Analysis:** Investigate seasonal patterns and external factors that influence demand more deeply.
