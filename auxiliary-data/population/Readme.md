# European Countries Population Data

This repository contains datasets related to the population distribution across various age groups for 30 European countries. Each file represents data for a specific country, including the total population segmented by age group.

## Datasets

### Sample File: Norway.csv

This dataset includes information on the population distribution for Norway.

- **Columns:**
  - `age_group`: The age group (e.g., 0-4, 5-9, etc.).
  - `population`: The total population in the specified age group.
 
- **Age Groups Covered:**
  - 0-4
  - 5-9
  - 10-14
  - 15-19
  - 20-24
  - 25-29
  - 30-34
  - 35-39
  - 40-44
  - 45-49
  - 50-54
  - 55-59
  - 60-64
  - 65-69
  - 70-74
  - 75-79
  - 80-84
  - 85-89
  - 90+

- **Sample Data:**
  ```csv
  age_group,population
  0-4,273874
  5-9,298418
  10-14,322876
  15-19,328313
  20-24,334883
  ```

### Files for Other Countries

In the folder, you will find similar CSV files for each of the 30 European countries. Each file follows the same format as described above, providing detailed population data by age group.

## Usage

These datasets can be used to analyze the population distribution across different age groups for European countries. The data is structured to allow for demographic analysis and comparison across different countries.

### Example Analysis

To get started with analyzing this data, you can use Python and pandas as follows:

```python
import pandas as pd

# Load the dataset for Norway
norway_df = pd.read_csv('Norway.csv')

# Display the first few rows of the dataset
print(norway_df.head())

# Example: Total population in Norway
total_population_norway = norway_df['population'].sum()
print(f"Total population in Norway: {total_population_norway}")

# Load the dataset for another country (e.g., Sweden)
sweden_df = pd.read_csv('Sweden.csv')

# Example: Compare total population between Norway and Sweden
total_population_sweden = sweden_df['population'].sum()
print(f"Total population in Sweden: {total_population_sweden}")
```