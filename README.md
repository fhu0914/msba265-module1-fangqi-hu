# MSBA 265 - Module 1: Exploratory Data Analysis

**Student:** Fangqi Hu  
**Course:** MSBA 265 - Business Analytics Topics  
**Instructor:** Shyla Solis  

## Project Overview

This repository contains the work completed for Module 1 of MSBA 265.

The project performs exploratory data analysis (EDA) on the French Motor Third Party Liability Claims dataset. The analysis focuses on data quality, business definitions, feature distributions, skewness, correlation, and outlier diagnostics before downstream modeling.

## Dataset

Dataset: French Motor Third Party Liability Claims  
OpenML ID: 41214

The dataset contains 678,013 policy records and 12 features related to insurance exposure, claims, driver characteristics, vehicle characteristics, geographic risk, and population density.

The raw dataset can be reproduced by running:

```powershell
python data\download_data.py
