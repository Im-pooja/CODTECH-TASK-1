# CODTECH Internship: Task 1 - Big Data Analysis

## Overview
This directory contains the code and output for Task 1 of the CODTECH internship, focusing on big data analysis using Python and Pandas. The analysis uses the `simple-zipcodes.csv` dataset, which contains 20 records with columns: `RecordNumber`, `Country`, `City`, `Zipcode`, and `State`. To demonstrate scalability, a synthetic dataset of 100,000 rows is generated. The analysis includes:
- Distribution of zip codes by state.
- Top 10 cities by frequency.
- Average record number by state for data validation.

## Files
- `task1_big_data_analysis.py`: Python script that generates the synthetic dataset and performs the analysis.
- `task1_output.txt`: Expected console output for the script, including dataset details and analysis results.
- `simple-zipcodes.csv`: Original dataset used for schema and sampling.

## Setup Instructions
1. **Install Dependencies**:
   - Create a fresh Anaconda environment:
     ```cmd
     conda create -n task1_env python=3.9
     conda activate task1_env
     pip install pandas
     ```
2. **Run the Script**:
   - Place `task1_big_data_analysis.py` and `simple-zipcodes.csv` in your working directory (e.g., `c:\Users\pooja`).
   - Navigate to the directory:
     ```cmd
     cd c:\Users\pooja
     ```
   - Execute the script:
     ```cmd
     python task1_big_data_analysis.py
     ```
3. **View Output**:
   - The script prints the dataset head, size, missing values, analysis results, and insights to the console.
   - Compare with `task1_output.txt` for expected output.

## Analysis Summary
- **Zip Code Distribution**: The synthetic dataset shows a near-uniform distribution across states (PR, FL, TX, AL, NC, AZ), with ~16,500-16,700 records per state, due to random sampling.
- **Top Cities**: Cities like ASHEBORO and MESA dominate, with ~5,500-5,600 records each.
- **Data Validation**: Average record numbers (~50,000 per state) confirm uniform data generation.
- **Scalability**: The synthetic dataset (100,000 rows) demonstrates the ability to handle large datasets using Pandas.
- **Conclusion**: This analysis showcases efficient processing of large datasets, with potential for additional metrics like unique zip codes in real-world applications.

## Notes
- Due to persistent execution issues with PySpark 4.0.0 on the local system, this task uses Pandas for reliable analysis.
- The expected output is provided in `task1_output.txt` to ensure a complete deliverable.
- If a larger dataset is available (e.g., NYC Yellow Taxi Trip Data), the script can be adapted for real-world big data analysis.
- Contact the internship coordinator for clarification on task requirements or dataset usage.

## Sample simple-zipcodes.csv Creation
If you don't have `simple-zipcodes.csv`, generate it with:
```python
import pandas as pd
sample_data = [
    (1, "US", "PARC PARQUE", "704", "PR"),
    (2, "US", "PASEO COSTA DEL SUR", "709", "PR"),
    (3, "US", "BDA SAN LUIS", "709", "PR"),
    (4, "US", "HOLT", "32564", "FL"),
    (5, "US", "HOMOSASSA", "34487", "FL"),
    # Add more rows up to 20 as needed
]
df_sample = pd.DataFrame(sample_data, columns=["RecordNumber", "Country", "City", "Zipcode", "State"])
df_sample.to_csv("simple-zipcodes.csv", index=False)


