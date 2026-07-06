# Hierarchical Bayesian Housing Price Prediction

A Bayesian machine learning project that predicts U.S. housing prices using a hierarchical regression model implemented in **R** and **Stan**. The project compares a traditional multiple linear regression baseline against a multilevel Bayesian model that captures differences across cities and states.

---

## Overview

This project investigates whether incorporating geographic hierarchy improves housing price prediction.

Using a sample of real estate listings from a large U.S. housing dataset, the analysis models housing prices as a function of:

- Square footage
- Lot size (acres)

while allowing model parameters to vary by:

- City
- State

The hierarchical Bayesian model is compared against a standard linear regression baseline to evaluate improvements in predictive performance.

---

## Dataset

The original dataset comes from a publicly available U.S. real estate dataset on Kaggle.

Because the full dataset is extremely large, a cleaned random sample of **5,000 homes** was created.

### Data preprocessing included

- Removing missing values
- Removing extreme outliers
- Filtering homes with:
  - Price > \$10,000,000
  - Lot size > 50 acres
  - Square footage > 10,000 sq ft
- Sampling homes from five states:
  - California
  - Massachusetts
  - Michigan
  - Texas
  - Florida
- Standardizing continuous variables using z-scores
- Encoding city and state as hierarchical grouping variables

---

## Project Structure

```
.
├── FinalProjectEDA.Rmd                     # Exploratory data analysis
├── FinalProjectDataSampling.Rmd            # Data cleaning and sampling
├── FinalProjectHierarchicalTesting.Rmd     # Model evaluation and testing
├── DataSci451FinalProjectHierarchicalModel.Rmd
├── FinalProjectCode.Rmd                    # Complete project workflow
├── realtor-data.zip.csv                    # Dataset
├── sample*.csv                             # Sample datasets
├── DataSci_451_Final_Project_Report.pdf    # Final report
├── DataSci 451 Final Project Presentation.pdf
└── Archive/                                # Previous versions
```

---

## Methodology

### 1. Exploratory Data Analysis

- Distribution of housing prices
- Relationship between square footage and acreage
- Outlier detection
- Feature inspection

### 2. Baseline Model

A multiple linear regression using:

- Square footage
- Acres

This model ignores geographic differences and serves as a baseline.

### 3. Hierarchical Bayesian Model

The Bayesian model allows regression coefficients to vary across cities and states.

Features include:

- Partial pooling across locations
- State-level effects
- City-level effects
- Posterior predictive distributions
- Bayesian parameter estimation using Stan

---

## Technologies Used

- **R**
- **Stan**
- **rstan**
- **ggplot2**
- **dplyr**
- **Bayesian Hierarchical Modeling**

---

## Results

The project compares:

- Baseline linear regression
- Hierarchical Bayesian regression

using:

- In-sample R²
- Posterior predictive distributions
- City-level comparisons
- State-level variation

The hierarchical model provides greater modeling flexibility by capturing geographic variation that is ignored by traditional regression.

---

## Repository Contents

| File | Description |
|------|-------------|
| `FinalProjectCode.Rmd` | Complete project workflow |
| `FinalProjectEDA.Rmd` | Exploratory data analysis |
| `FinalProjectDataSampling.Rmd` | Data cleaning and sampling |
| `FinalProjectHierarchicalTesting.Rmd` | Model evaluation |
| `DataSci451FinalProjectHierarchicalModel.Rmd` | Bayesian hierarchical model implementation |
| `DataSci_451_Final_Project_Report.pdf` | Full project report |
| `DataSci 451 Final Project Presentation.pdf` | Presentation slides |

---

## Future Improvements

Potential extensions include:

- Cross-validation for model evaluation
- Additional housing features (bedrooms, bathrooms, year built, etc.)
- Spatial modeling using geographic coordinates
- Time-series analysis of housing prices
- More advanced Bayesian priors and model comparison techniques

---

## Authors

- Skye Chao
- Myles Liss-Riordan
