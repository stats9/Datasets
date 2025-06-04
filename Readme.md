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