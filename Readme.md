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
  - Type: Weighted decile measurement
  - Unit: Index value between 0-1
  - Source: Statistical Center of Iran (amar.org.ir)
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