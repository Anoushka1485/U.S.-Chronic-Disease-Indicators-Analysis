# U.S. Chronic Disease Indicators Analysis

## Overview
An end-to-end data analysis project on the CDC's U.S. Chronic Disease Indicators (CDI) 
dataset, covering 309,215 records across all U.S. states and territories from 2015–2022. 
The project applies systematic data cleaning, exploratory data analysis, and formal 
statistical methods to identify meaningful patterns in chronic disease burden across 
the United States.

## Dataset
- **Source:** U.S. Centers for Disease Control and Prevention (CDC) via data.gov
- **Title:** U.S. Chronic Disease Indicators (CDI)
- **Raw Size:** 309,215 rows × 34 columns
- **Cleaned Size:** 188,885 rows × 20 columns
- **Coverage:** 2015–2022 | All U.S. states and territories | 18 disease topics

## Project Structure
```
cdi-analysis/
├── data/
│   └── U.S._Chronic_Disease_Indicators.csv
├── notebooks/
│   └── cdi_analysis.ipynb
├── figures/
│   ├── fig1_trend_over_time.png
│   ├── fig2_top10_topics.png
│   ├── fig3_data_source_distribution.png
│   ├── fig4_top10_states.png
│   ├── fig5_correlation_heatmap.png
│   ├── fig6_normality_test.png
│   ├── fig7_confidence_intervals.png
│   └── fig8_linear_regression.png
├── requirements.txt
└── README.md
```

## Methodology

### 1. Data Cleaning
- Assessed and handled missing values across 34 columns
- Dropped columns with excessive missing values and limited analytical utility
- Applied forward fill for remaining missing `DataValue` entries
- Converted high-cardinality object columns to categorical dtype
- Retained `LocationDesc` and `LocationAbbr` as readable categorical columns

### 2. Exploratory Data Analysis (EDA)
- **Line Chart:** Average chronic disease indicator trend over time (2015–2022)
- **Horizontal Bar Chart:** Top 10 disease topics by average rate
- **Pie Chart:** Distribution of records by data source
- **Bar Chart:** Top 10 U.S. states by average disease rate
- **Correlation Heatmap:** Linear relationships across numeric variables

### 3. Statistical Analysis
- **Shapiro-Wilk Normality Test:** Confirmed right-skewed distribution (W=0.5408, p≈0.000)
- **Independent T-Test:** Significant decline in disease rates pre vs. post 2019 (t=43.52, p≈0.000)
- **95% Confidence Intervals:** Plotted per disease topic using existing confidence limit columns

### 4. Advanced Analysis
- **Linear Regression:** YearStart as predictor of mean annual DataValue
  - Slope: -12.66 (units/year)
  - R²: 0.8651
  - p-value: 0.002388

## Key Findings
- **Cancer** has the highest average disease rate (mean: 100.08), followed by Maternal 
  Health (87.88) and COPD (78.06)
- Average chronic disease rates **declined significantly** from 2015–2022 
  (regression slope = -12.66, R²=0.87)
- **BRFSS** dominates data collection, accounting for 71.2% of all records
- **West Virginia, Oklahoma, Mississippi** rank among the highest-burden states
- DataValue distribution is **strongly right-skewed** — validating use of 
  non-parametric methods

## Technologies Used
| Tool | Purpose |
|------|---------|
| Python | Core analysis language |
| Pandas | Data cleaning and transformation |
| Matplotlib | Static visualizations |
| SciPy | Statistical testing and regression |
| NumPy | Numerical computations |

## Installation
```bash
git clone https://github.com/Anoushka1485/cdi-analysis.git
cd cdi-analysis
pip install -r requirements.txt
jupyter notebook notebooks/cdi_analysis.ipynb
```

## Requirements
```
pandas
matplotlib
scipy
numpy
jupyter
```


## Course
IE6600 — Computation and Visualization for Analytics
Northeastern University | Group 7
