# Predicting School Performance from Socioeconomic Factors

> An analysis exploring whether school performance, measured by average ACT scores, can be predicted by socioeconomic conditions across U.S. schools in 2016–2017.

---

## Project Overview

This project examines the relationship between school performance and socioeconomic context using publicly available datasets. The analysis evaluates whether factors such as unemployment rate, college attainment, and the proportion of students receiving free or reduced-price lunch predict differences in average ACT scores among U.S. schools.

- **Objective:** Understanding how socioeconomic disadvantage relates to school performance.  
- **Domain:** Education 
- **Key Techniques:** Regression

---

## Project Structure

```
├── data/                 # Raw and processed data
├── code/                 # Jupyter notebooks and Python scripts
├── reports/              # Generated reports and visualizations
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

---

## Data

- **Sources:**
  - [EdGap.org](https://www.edgap.org/) — Socioeconomic indicators by school  
  - [Common Core of Data (CCD) – NCES](https://nces.ed.gov/ccd/) — School-level information  
  - [ACS 2013–2017 (U.S. Census Bureau)](https://api.census.gov/data/2017/acs/acs5/subject) — Regional socioeconomic measures (e.g., unemployment, education levels)  

- **Coverage:**  
  School- and state-level data for the 2016–2017 school year across 20 U.S. states.  

- **License:**  
  Publicly available open data provided by NCES and the U.S. Census Bureau.  

---

## Analysis

The analysis was performed in the notebook **`Education.ipynb`**, using data from the `data/` directory.

### Steps
1. **Data Preparation**
   - Load and merge EdGap, CCD, and ACS datasets  
   - Remove duplicates and handle missing values  
   - Convert units (e.g., percent to fraction)  

2. **Feature Selection**
   - Chosen predictors:  
     `rate_unemployment`, `percent_college`, and `percent_lunch`

3. **Exploratory Analysis**
   - Descriptive statistics and correlation matrices  
   - Scatterplots and pairplots to visualize relationships  

4. **Modeling**
   - Reduced Ordinary Least Squares (OLS) model:  
     `average_act ~ rate_unemployment + percent_college + percent_lunch`  
   - Evaluate model fit (R², Adj. R²) and statistical significance  

5. **Results Communication**
   - Exported formatted tables (`desc.csv`, `corr.csv`, `regression.csv`)  
   - Final report: `education_report_with_tables.docx`  

---

## Results

| Predictor | Coefficient | p-value | Direction |
|------------|--------------|----------|-----------|
| Unemployment rate | −2.17 | < 0.001 | Negative |
| College graduates (%) | +1.72 | < 0.001 | Positive |
| Free/reduced lunch (%) | −7.59 | < 0.001 | Negative |

- **Model Fit:** R² = 0.78, Adj. R² = 0.78, N = 7,227  
- **Key Findings:**  
  - Schools with higher economic disadvantage (higher unemployment and lunch participation) tend to have lower ACT scores.  
  - Educational attainment (college graduates) correlates positively with school performance.  
- **Limitations:**  
  - Dataset covers 20 states (not nationally representative).  
  - Indicators are regional averages, not individual student data.  ```

---

## Authors

**Ben Jessop**  
- GitHub: [@benjaminjonjessop](https://github.com/benjaminjonjessop)  
- Seattle University Data Science Certificate Program  

---

## License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- Seattle University Faculty for guidance on data science methodology  
- Tools: `pandas`, `statsmodels`, `seaborn`, `plotly`  
- Data providers: NCES and the U.S. Census Bureau  
