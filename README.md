# Humidity vs Electricity Demand (AEMO + BOM)

This project explores how **humidity** relates to **electricity demand** across Australian states, and how the relationship changes under different temperatures.

## Project Overview
This repository analyses the relationship between **humidity and electricity demand** across Australian states using data from:

- **AEMO demand data** (half-hourly electricity total demand for Australian states)
- **Bureau of Meteorology weather files** containing humidity and temperature metrics

The goal is to understand whether humidity affects electricity demand — especially under different temperature conditions — by using exploratory analysis and regression modelling with interaction effects.

## Project Highlights
- Cleaned and merged **AEMO demand** with **BOM weather** data
- Exploratory analysis across states and seasons
- Regression with **non-linear temperature effects (Temperature²)** and **Humidity×Temperature interaction**
- Marginal-effect plot showing humidity impact increases at higher temperatures

## Tech Stack
- **Programming Language:** Python
- **Data Analysis:** pandas, NumPy
- **Visualisation:** matplotlib, seaborn
- **Machine Learning / Modelling:** scikit-learn
- **Data Sources:** AEMO (electricity demand), Bureau of Meteorology (weather)
- **Version Control:** Git, GitHub

## Key Skills Demonstrated
- Data cleaning and preprocessing of large time-series datasets
- Merging heterogeneous data sources (energy demand and weather data)
- Feature engineering, including non-linear and interaction terms
- Exploratory data analysis across multiple geographic regions
- Regression modelling and interpretation of coefficients
- Marginal-effect analysis for interaction terms
- Clear communication of results through visualisations and documentation
- Reproducible project structure and version control using GitHub
  
## Repository Structure
- `notebooks/`
  - `humidity_temp_data_processing_all_states.ipynb` – data processing and merging
  - `humidity_demand_eda.ipynb` – EDA + regression + interpretation
- `data/`
  - `raw/` – excluded from GitHub (large files)
  - `processed/` – small sample

## Data Availability
Due to file size constraints, full raw and processed datasets are not included in this repository.

A small **processed sample dataset** is provided in:
- `data/processed/sample_master_data.csv`

This sample preserves the full schema and formatting of the original data and can be used to run and inspect the notebooks. Instructions for reproducing the full dataset are provided in the notebooks.

### Sample Data Schema
| Column Name      | Description                                  |
|------------------|----------------------------------------------|
| Datetime         | Timestamp (half-hourly)                      |
| State            | Australian state                             |
| Total Demand     | Electricity demand (MW)                      |
| Humidity (%)     | Relative humidity (%)                        |
| Temperature      | Air temperature (°C)                         |


## Results
- Exploratory analysis shows that **humidity alone has a weak direct relationship** with electricity demand across states.
- Electricity demand is primarily driven by **temperature**, with strong non-linear effects captured using a quadratic temperature term.
- When modelled jointly with temperature, **humidity exhibits a conditional effect**, becoming increasingly important at higher temperatures.
- Marginal-effect analysis demonstrates that higher humidity **amplifies electricity demand during hot conditions**, consistent with increased cooling load and reduced thermal comfort.
- State fixed effects account for substantial baseline differences in demand, reflecting population size, climate, and industrial structure.
- Overall, findings suggest that humidity’s influence on electricity demand is **strongest when considered alongside temperature**, particularly in hotter conditions.

## How to Run
1. Create an environment and install dependencies:
   ```bash
   pip install -r requirements.txt
2. Place raw files into:
   `data/raw/demand/` (AEMO CSVs)
   `data/raw/weather/` (BOM files)
3. Run the processing notebook, then the EDA notebook.

## Future Work
Possible extensions include:
- Adding weather station coverage variation analysis
- Including other variables like wind or solar exposure
- Building a multivariate forecasting model for demand under humidity/temperature conditions
