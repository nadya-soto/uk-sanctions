
# Sanctions Data Engineering 

## Overview
This project processes the UK financial sanctions list and transforms it into a structured dataset suitable for comparison with customer databases or integration into compliance workflows.

## Project Structure


  ├── data/
  
  │   └── UK\_Sanctions\_List.xlsx         # Raw input data
  
  ├── output/
  
  │   └── UK\_Sanctions\_Processed.csv     # Cleaned and structured data
  
  ├── scripts/
  
  │   ├── transform\_sanctions\_data.py    # Main data processing script
  
  │   └── transform\_notebook.ipynb       # Exploratory notebook version
  
  ├── env/                               # Python virtual environment (not uploaded)
  
  ├── requirements.txt                   # List of dependencies
  
  └── README.md                          # Project documentation


## Code Files

- `scripts/transform_sanctions_data.py`  
  Main script that parses, cleans, and structures the UK sanctions list.

- `scripts/transform_notebook.ipynb`  
  Jupyter notebook used for exploratory data analysis and prototyping.

## Requirements

- Python 3.7+
- pandas
- numpy
- openpyxl

To install the dependencies:

```bash
pip install -r requirements.txt
streamlit run scripts/app.py

````


## Usage

1. Place the raw Excel file in the `data/` directory (named `UK_Sanctions_List.xlsx`).
2. Run the processing script:

```bash
python scripts/transform_sanctions_data.py
```

3. The processed data will be saved to:

```
output/UK_Sanctions_Processed.csv
```

## Data Quality Notes

Key data issues in the original dataset:

* Missing Date of Birth: 1,782 records (\~38%)
* Missing Addresses: 2,487 records (\~53%)
* Missing Nationality: 2,092 records (\~45%)
* Missing Related Countries: 733 records (\~16%)
* Duplicate Primary Names: 3 duplicate records found

No missing values were found for:

* Group Type
* Primary Name
* Aliases
* Regime
* Other Information

## Output Fields

The cleaned dataset includes the following fields:

| Field               | Description                                                    |
| ------------------- | -------------------------------------------------------------- |
| `group_id`          | Unique identifier for each entity                              |
| `group_type`        | Type of entity (e.g., individual, organization)                |
| `primary_name`      | Main name of the sanctioned entity                             |
| `aliases`           | Other known names                                              |
| `addresses`         | Associated addresses                                           |
| `regime`            | Relevant sanctions regime                                      |
| `related_countries` | Countries related to the entity (e.g., residence, operations)  |
| `nationality`       | Declared nationality                                           |
| `other_information` | Additional context or descriptive details                      |
| `dates`             | Includes date of birth, listing date, designation, last update |

## Potential Applications

* Compliance and sanctions screening
* AML/KYC integration
* Risk analysis systems
* Support for due diligence processes

