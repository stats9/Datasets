# Datasets Repository

This repository contains various datasets used for data analysis and machine learning projects.

## Repository Structure

```
datasets/
├── raw/           # Original, immutable data dumps
├── processed/     # Cleaned, transformed and processed data
└── external/      # Data from third party sources
```

## Datasets Overview

| Dataset Name | Description | Source | Last Updated |
|--------------|-------------|---------|--------------|
| datlabeled1  | 4 explantory and quantitative variables and one class variables | [link](https://github.com/stats9/Datasets/blob/main/processed/datlabeled1.xlsx) | 2025-05-30 |
| SCOREDATA | Student reading comprehension scores comparing three teaching methods with 15 repetitions each | [link](processed/SCOREDATA.xlsx) | 2025-06-04 |
| UNEMPLOYMENT_IR | Seasonal unemployment rate for ages 15-24 in Iran (1384-1403) | [link](https://amar.org.ir/statistical-information/statid/21889) | 2025-06-06 |
| GDP_Weighted_Iran | Weighted decile Gini Coefficient in Iran (1363-1402) | [link](https://amar.org.ir/statistical-information/statid/21861) | 2025-06-06 |
| CustomerSegmentation | Customer segmentation data with demographic and spending information | [link](processed/CustomerSegmentation.xlsx) | 2025-06-08 |
| PatientGroups | Patient health metrics for grouping analysis | [link](processed/PatientGroups.xlsx) | 2025-06-08 |
| StudentPerformance | Student academic performance across multiple subjects | [link](processed/StudentPerformance.xlsx) | 2025-06-08 |
| FraudDetection | Transaction data for fraud detection analysis | [link](processed/FraudDetection.xlsx) | 2025-06-08 |
| DiseaseDetection | Patient medical data for disease diagnosis | [link](processed/DiseaseDetection.xlsx) | 2025-06-08 |
| LoanApproval | Loan applicant data for approval prediction | [link](processed/LoanApproval.xlsx) | 2025-06-08 |
| Nobel_Prize_Clean | Structured dataset of Nobel Prize laureates including year, category, motivation, country of birth, and affiliations | [link](processed/nobel_prize_clean.csv) | 2025-12-04 |


## Data Dictionary

### datlabeled1
Please refer to the dataset documentation in its folder.

### SCOREDATA
- **Method**: Teaching method (Categorical)
  - Traditional: Conventional teaching approach (15 samples)
  - Active: Interactive learning method (15 samples)
  - Digital: Technology-based teaching method (15 samples)
- **Score**: Reading comprehension scores (Numeric)
  - Range: 11.0-18.6
  - Scale: 20-point scale
  - Total observations: 45 (15 per method)

### UNEMPLOYMENT_IR
- **Date**: Time period (Seasonal)
  - Range: 1384 to 1403 (Iranian Calendar)
  - Frequency: Quarterly (4 observations per year)
- **Rate**: Unemployment rate (Numeric)
  - Population: Ages 15-24 years
  - Unit: Percentage (%)
  - Source: Statistical Center of Iran (amar.org.ir)
  
### GDP_Weighted_Iran
- **Year**: Time period (Annual)
  - Range: 1363 to 1402 (Iranian Calendar)
  - Frequency: Yearly
- **Coefficient**: Gini Coefficient (Numeric)
  - Type: Gini Index Coefficient Not Weighted
  - Unit: Index value between 0-1
  - Source: Statistical Center of Iran (amar.org.ir)

### CustomerSegmentation (100 observations)
- **CustomerID**: Unique identifier for each customer (Integer)
- **Age**: Customer age in years (Numeric)
- **Income**: Annual income in dollars (Numeric)
- **SpendingScore**: Customer spending score (Scale 1-100)

### PatientGroups (150 observations)
- **PatientID**: Unique identifier for each patient (Integer)
- **BloodPressure**: Systolic blood pressure in mmHg (Numeric)
- **Cholesterol**: Blood cholesterol level in mg/dL (Numeric)
- **BMI**: Body Mass Index in kg/m² (Numeric)

### StudentPerformance (120 observations)
- **StudentID**: Unique identifier for each student (Integer)
- **MathScore**: Mathematics score (Scale 0-100)
- **ScienceScore**: Science score (Scale 0-100)
- **ReadingScore**: Reading comprehension score (Scale 0-100)

### FraudDetection (200 observations)
- **TransactionID**: Unique identifier for each transaction (Integer)
- **Amount**: Transaction amount in dollars (Numeric)
- **Frequency**: Monthly transaction frequency (Numeric)
- **BalanceHistory**: Account balance history in dollars (Numeric)
- **FraudLabel**: Fraud status (Categorical: "Fraud" or "Not Fraud")

### DiseaseDetection (250 observations)
- **PatientID**: Unique identifier for each patient (Integer)
- **BloodSugar**: Blood sugar level in mg/dL (Numeric)
- **BloodPressure**: Systolic blood pressure in mmHg (Numeric)
- **Cholesterol**: Blood cholesterol level in mg/dL (Numeric)
- **DiseaseStatus**: Disease status (Categorical: "Yes" or "No")

### LoanApproval (180 observations)
- **ApplicantID**: Unique identifier for each loan applicant (Integer)
- **Income**: Annual income in dollars (Numeric)
- **CreditScore**: Credit score (Scale 500-850)
- **ExistingDebt**: Current debt amount in dollars (Numeric)
- **LoanApproval**: Loan approval status (Categorical: "Approved" or "Rejected")


### Nobel_Prize_Clean
- **Year**: Year of the award (Numeric, 1901–2025)  
- **Category**: Prize category (Categorical: "physics", "chemistry", "medicine", "peace", "literature", "economics")  
- **Laureate_ID**: Unique identifier for each laureate (Integer)  
- **Name**: Full name of the laureate (String)  
- **Motivation**: Official Nobel Committee statement for awarding the prize (String)  
- **Share**: Share of the prize when divided among multiple laureates (Numeric: 1, 2, 3, …)  
- **Born_Country**: Country of birth of the laureate (String)  

## Usage

```python
# Example code for loading a dataset
import pandas as pd
import requests
from io import BytesIO

# Load SCOREDATA directly from GitHub
url = "https://github.com/stats9/Datasets/raw/main/processed/SCOREDATA.xlsx"
response = requests.get(url)
scores = pd.read_excel(BytesIO(response.content))
```

```python
# Load UNEMPLOYMENT_IR data from GitHub
url = "https://github.com/stats9/Datasets/raw/main/processed/UNEMPLOYMENT_IR.xlsx"
response = requests.get(url)
unemployment = pd.read_excel(BytesIO(response.content))
```

```python
# Load GDP_Weighted_Iran data from GitHub
url = "https://github.com/stats9/Datasets/raw/main/processed/GDP_Weighted_Iran.xlsx"
response = requests.get(url)
gini_coef = pd.read_excel(BytesIO(response.content))
```


```python
import pandas as pd

url = "https://github.com/stats9/Datasets/raw/main/processed/nobel_prize_clean.csv"
nobel = pd.read_csv(url)
print(nobel.head())
```


```r
# Load SCOREDATA in R directly from GitHub
library(readxl)
url <- "https://github.com/stats9/Datasets/raw/main/processed/SCOREDATA.xlsx"
temp <- tempfile()
download.file(url, temp, mode = "wb")
scores <- read_excel(temp)
unlink(temp)
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Add your datasets
4. Update the README with dataset information
5. Submit a Pull Request

## License

This project is licensed under the MIT License:

```
MIT License

Copyright (c) 2025 stats9
```

## Contact

For questions or concerns about the datasets, please open an issue in this repository.