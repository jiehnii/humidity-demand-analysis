# Humidity vs Electricity Demand (AEMO + BOM)

This project explores how **humidity** relates to **electricity demand** across Australian states, and how the relationship changes under different temperatures.

## Project Highlights
- Cleaned and merged **AEMO demand** with **BOM weather** data
- Exploratory analysis across states and seasons
- Regression with **non-linear temperature effects (Temperature²)** and **Humidity×Temperature interaction**
- Marginal-effect plot showing humidity impact increases at higher temperatures

## Repository Structure
- `notebooks/`
  - `humidity_temp_data_processing_all_states.ipynb` – data processing and merging
  - `humidity_demand_eda.ipynb` – EDA + regression + interpretation
- `data/`
  - `raw/` – excluded from GitHub (large files)
  - `processed/` – small sample

## How to Run
1. Create an environment and install dependencies:
   ```bash
   pip install -r requirements.txt
2. Place raw files into:
   `data/raw/demand/` (AEMO CSVs)
   `data/raw/weather/` (BOM files)
3. Run the processing notebook, then the EDA notebook.

## Data Availability

Due to file size constraints, full raw and processed datasets are not included in this repository.

A small **processed sample dataset** is provided in:
- `data/processed/sample_master_data.csv`

This sample preserves the full schema and formatting of the original data and can be used to run and inspect the notebooks. Instructions for reproducing the full dataset are provided in the notebooks.

## Results

- Exploratory analysis shows that **humidity alone has a weak direct relationship** with electricity demand across states.
- Electricity demand is primarily driven by **temperature**, with strong non-linear effects captured using a quadratic temperature term.
- When modelled jointly with temperature, **humidity exhibits a conditional effect**, becoming increasingly important at higher temperatures.
- Marginal-effect analysis demonstrates that higher humidity **amplifies electricity demand during hot conditions**, consistent with increased cooling load and reduced thermal comfort.
- State fixed effects account for substantial baseline differences in demand, reflecting population size, climate, and industrial structure.
- Overall, the results highlight the importance of **model specification** and **interaction effects** when analysing weather–demand relationships.
