# Purchase Frequency Drives Annual Revenue at NovaRetail+ (Spearman ρ = 0.97)

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=plotly&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

Which customer behaviors are most strongly associated with annual revenue on NovaRetail+, a fictional e-commerce platform in Latin America? Monthly purchases show a very strong monotonic association with annual revenue (Spearman ρ = 0.97), while monthly website visits show only a low-to-moderate one (ρ = 0.32).

![Correlation heatmap](images/correlation_heatmap.png)

> **Important:** This is an exploratory, correlational analysis. The relationships are statistical associations and do not establish causality.

## Business Question

Which customer behaviors are most strongly associated with annual revenue, and where should further analysis focus? The answer gives NovaRetail+ an initial basis for customer segmentation, behavioral analysis, and opportunities to improve e-commerce performance.

## Data

- **Source:** NovaRetail+ dataset (fictional e-commerce platform, Latin America).
- **Files used:** *data/raw/novaretail_comportamiento_clientes_2024.csv
- **Key variables:** `annual_revenue`, `monthly_purchases`, `monthly_visits`, `targeted_ad_spend`, plus several categorical variables

## Process

- **Cleaning and validation (pandas):** Checked data types, missing values, and dataset consistency.
- **Exploratory data analysis:** Examined customer behavior and revenue-related patterns, and used descriptive statistics to understand distributions.
- **Correlation analysis**, with the method chosen by variable type:
  - Pearson for linear relationships between numeric variables
  - Spearman for monotonic relationships
  - Point-biserial for binary vs. numeric variables
  - Cramér's V for categorical vs. categorical variables
- **Visualization:** Heatmaps and scatter plots to explore and communicate relationships.

```python
# Example: Spearman correlation between purchase frequency and revenue
df["monthly_purchases"].corr(df["annual_revenue"], method="spearman")
```

## Findings

1. **Purchase frequency and revenue:** `monthly_purchases` has a very strong positive monotonic association with `annual_revenue` (Spearman ρ = 0.97).
2. **Website engagement and revenue:** `monthly_visits` has a low-to-moderate positive association with `annual_revenue` (Spearman ρ = 0.32).
3. **Advertising and traffic:** `targeted_ad_spend` has a moderate positive linear association with `monthly_visits` (Pearson r = 0.58).
4. **Other variables:** Most show weak associations with annual revenue, so simple correlation may not capture all patterns.
5. **Categorical variables:** Cramér's V found no strong associations among those examined.

## Recommendations

- Prioritize strategies that increase purchase frequency, since it is the behavior most closely tied to annual revenue.
- Do not rely on traffic alone as a revenue lever. Visits show only a modest association with revenue.
- Treat targeted ad spend as a traffic driver and test whether that traffic converts into purchases.
- Run customer segmentation analyses to uncover patterns that overall correlations do not show.

## Limitations

- Correlation does not imply causation, so the results cannot show that purchase frequency causes revenue.
- Pearson and Spearman capture only linear and monotonic relationships.
- Weak overall correlations may hide effects within specific customer segments.
- The dataset comes from a fictional platform, so results cannot be generalized to real businesses.

## How to Open

- Clone the repository and install the dependencies: `pip install -r requirements.txt`
- Open the notebook with Jupyter: `S8 Student Version-Project-NovaRetail.ipynb` 

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook
