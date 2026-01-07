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

## Notes
Raw datasets are not included due to size. The notebooks use relative paths so they run after cloning.
