# MSBA 265 - Module 1: Exploratory Data Analysis

**Student:** Fangqi Hu  
**Course:** MSBA 265 - Business Analytics Topics  
**Instructor:** Shyla Solis  

## Project Overview

This repository contains the work completed for Module 1 of MSBA 265.

The project performs exploratory data analysis (EDA) on the French Motor Third Party Liability Claims dataset. The analysis focuses on data quality, business definitions, feature distributions, skewness, correlation, and outlier diagnostics before downstream modeling.

This README provides step-by-step instructions for reproducing the project on another computer.

## Dataset

**Dataset:** French Motor Third Party Liability Claims  
**OpenML ID:** 41214

The dataset contains 678,013 policy records and 12 features related to insurance exposure, claims, driver characteristics, vehicle characteristics, geographic risk, and population density.

---

# Reproduction Instructions

## Step 1 - Clone the Repository

Open PowerShell or the VS Code terminal and run:

```powershell
git clone https://github.com/fhu0914/msba265-module1-fangqi-hu.git
```

Move into the project directory:

```powershell
cd msba265-module1-fangqi-hu
```

## Step 2 - Create a Virtual Environment

Create a Python virtual environment:

```powershell
python -m venv venv
```

Activate it in Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

If PowerShell blocks the activation script, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

Then activate the environment again:

```powershell
.\venv\Scripts\Activate.ps1
```

After successful activation, `(venv)` should appear at the beginning of the terminal prompt.

## Step 3 - Install Required Packages

Upgrade pip:

```powershell
python -m pip install --upgrade pip
```

Install all project dependencies:

```powershell
pip install -r requirements.txt
```

Wait until the installation finishes without errors.

## Step 4 - Download the Raw Dataset

From the project root directory, run:

```powershell
python data\download_data.py
```

Expected result:

```text
678,013 rows x 12 columns
```

The downloaded dataset will be saved as:

```text
data/raw_business_data.csv
```

## Step 5 - Run the EDA Notebook

Open the following notebook in Visual Studio Code:

```text
notebooks/01_eda_and_data_dictionary.ipynb
```

Select the Python kernel from the project's `venv`.

Then click **Run All** to execute all notebook cells from top to bottom.

The notebook performs:

- Structural and data quality audits
- Summary statistics
- Business data dictionary creation
- Skewness diagnostics
- Pearson correlation analysis
- Multicollinearity analysis
- Distribution visualization
- Outlier diagnostics

All notebook cells should run without runtime errors.

## Step 6 - Verify Notebook Outputs

After the notebook finishes, verify that the following outputs exist:

```text
reports/data_dictionary.csv
reports/figures/correlation_heatmap.png
reports/figures/feature_distributions.png
```

## Step 7 - Run the Outlier Cleaning Pipeline

From the project root directory, run:

```powershell
python src\clean_outliers.py
```

The script applies the Tukey 1.5 × IQR outlier filtering method to the `Density` feature.

Expected output:

```text
Initial Dataset Records: 678,013
Outlier Records Removed: 77,566 (11.44%)
Final Cleaned Records: 600,447
```

The cleaned dataset will be saved as:

```text
data/cleaned_business_data.csv
```

## Step 8 - Verify the Final Project

Confirm that:

- The dataset downloads successfully.
- The raw dataset contains 678,013 rows and 12 columns.
- The notebook runs from top to bottom without runtime errors.
- `reports/data_dictionary.csv` is generated.
- The correlation heatmap is generated.
- The feature distribution plots are generated.
- The outlier-cleaning script runs without runtime errors.
- The cleaned dataset is generated.
- `Module1 Homework Report.pdf` is available in the repository.

## Troubleshooting

### PowerShell cannot activate the virtual environment

Run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

Then run:

```powershell
.\venv\Scripts\Activate.ps1
```

### ModuleNotFoundError

Make sure the virtual environment is activated, then run:

```powershell
pip install -r requirements.txt
```

### Jupyter cannot find an installed package

Make sure the notebook is using the Python kernel from the project's `venv`, not the global Python installation.

### Dataset is missing

Make sure you are in the project root directory and run:

```powershell
python data\download_data.py
```

---

# Peer Replication Requirement

Before final submission, this repository must be independently tested by a classmate.

The peer reviewer should:

1. Clone this repository onto their own computer.
2. Follow only the instructions provided in this README.
3. Complete the setup without verbal assistance from the project submitter.
4. Run the complete workflow.
5. Confirm that the project executes without runtime errors.
6. Verify that the expected outputs are reproduced.
7. Complete and sign the Project Replication & Peer Verification Form.