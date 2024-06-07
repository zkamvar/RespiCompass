# COVID-19 Vaccination Data

This repository contains two datasets related to COVID-19 vaccination, split into two periods: before 2023 and after 2023.

## Datasets

### 1. covid_vax_pre23.csv

This dataset includes vaccination data up to the end of 2022.

- **Columns:**
  - `date`: The date of the record in YYYY-MM-DD format.
  - `location_name`: The name of the location (country or region).
  - `iso2_code`: The ISO 3166-1 alpha-2 code of the location.
  - `target_group`: The demographic group targeted by the vaccination (e.g., ALL, Age25_49, HCW, LTCF).
  - `dose`: The type of dose administered (e.g., FirstDose, SecondDose).
  - `doses_administered`: The number of doses administered.

- **Sample Data:**
  ```csv
  date,location_name,iso2_code,target_group,dose,doses_administered
  2020-12-20,Denmark,DK,ALL,FirstDose,2
  2020-12-20,Denmark,DK,Age25_49,FirstDose,2
  2020-12-20,Denmark,DK,HCW,FirstDose,0
  2020-12-20,Denmark,DK,LTCF,FirstDose,0
  2020-12-27,Denmark,DK,ALL,FirstDose,9
  ```

### 2. covid_vax_post23.csv

This dataset includes vaccination data from the beginning of 2023 onwards.

- **Columns:**
  - `date`: The date of the record in YYYY-MM-DD format.
  - `location_name`: The name of the location (country or region).
  - `iso2_code`: The ISO 3166-1 alpha-2 code of the location.
  - `target_group`: The demographic group targeted by the vaccination (e.g., ALL).
  - `dose`: The type of dose administered (in this dataset, this column is NaN for all rows).
  - `doses_administered`: The number of doses administered.

- **Sample Data:**
  ```csv
  date,location_name,iso2_code,target_group,dose,doses_administered
  2023-09-30,Belgium,BE,ALL,,431019
  2023-09-30,Bulgaria,BG,ALL,,3455
  2023-09-30,Cyprus,CY,ALL,,1093
  2023-09-30,Czechia,CZ,ALL,,14003
  2023-09-30,Germany,DE,ALL,,201281
  ```

## Usage

These datasets can be used to analyze the trends and patterns in COVID-19 vaccination over time. The data is structured to allow for time-series analysis and comparison across different locations and demographic groups.

### Example Analysis

To get started with analyzing this data, you can use Python and pandas as follows:

```python
import pandas as pd

# Load datasets
pre23_df = pd.read_csv('covid_vax_pre23.csv')
post23_df = pd.read_csv('covid_vax_post23.csv')

# Display the first few rows of each dataset
print(pre23_df.head())
print(post23_df.head())

# Example: Total doses administered in 2022
total_doses_2022 = pre23_df[pre23_df['date'] < '2023-01-01']['doses_administered'].sum()
print(f"Total doses administered in 2022: {total_doses_2022}")

# Example: Total doses administered in 2023
total_doses_2023 = post23_df['doses_administered'].sum()
print(f"Total doses administered in 2023: {total_doses_2023}")
```