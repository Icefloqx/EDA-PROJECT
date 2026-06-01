# 🇰🇪 Kenya Development Story
### An Exploratory Data Analysis of Six Decades of Progress

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com)
[![Data Source](https://img.shields.io/badge/Data-World%20Bank%20WDI-009FDA?style=flat-square)](https://databank.worldbank.org)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=flat-square)](LICENSE)

---

> *"Data is not just numbers — it is the story of a nation, its people, and their aspirations."*

This project presents a comprehensive exploratory data analysis of Kenya's development trajectory from **1960 to 2025**, using the World Bank's World Development Indicators (WDI) dataset. Spanning 1,486 indicators across economics, health, education, trade, and digital infrastructure, the analysis uncovers the patterns, shocks, and milestones that have shaped modern Kenya.

---

##  Preview

| Economy & GDP | Health & Demographics |
|:-:|:-:|
| GDP growth bars, per capita trend | Life expectancy by gender, infant mortality |

| Education | Digital & Infrastructure |
|:-:|:-:|
| Enrollment by level, gender parity | Mobile boom, internet adoption curve |

> Run the notebook to generate all visualisations interactively.

---

##  Project structure

```
kenya-wdi-eda/
│
├── kenya_wdi_eda.ipynb              # Main EDA notebook
├── API_KEN_DS2_en_csv_v2_5938.csv  # World Bank WDI dataset (Kenya)
├── README.md                        # This file
```

---

##  Dataset

| Attribute | Details |
|---|---|
| **Source** | [World Bank — World Development Indicators](https://databank.worldbank.org/source/world-development-indicators) |
| **Country** | Kenya (KEN) |
| **Coverage** | 1960 – 2025 |
| **Total indicators** | 1,486 |
| **Indicators with recent data (2015–2023)** | 1,283 (86%) |
| **Format** | CSV (wide format — years as columns) |
| **File** | `API_KEN_DS2_en_csv_v2_5938.csv` |

The dataset follows the standard World Bank WDI structure: rows are indicators, columns are years, and the first four rows are metadata (skipped on load).

---

##  Notebook structure

The notebook is organised into **9 sections**, designed to tell a coherent story from data quality through to cross-theme insights.

### 1 · Setup & data loading
- Imports and plot styling configuration
- CSV loading with metadata/year column separation
- Reusable `get_series(indicator_name)` helper function

### 2 · Dataset overview & quality audit
- Missing data heatmap across 60 sampled indicators
- Indicator category breakdown by World Bank code prefix
- Coverage statistics for recent years

### 3 · Economy & GDP
- GDP (absolute, USD billions) — 1960 to 2023
- Annual GDP growth rate with recession highlighting
- GDP per capita trend
- Consumer price inflation with mean reference line
- Decade-average growth rate comparison

### 4 · Health & demographics
- Life expectancy by total, female, and male
- Total population growth (millions)
- Birth rate vs death rate with natural increase shading
- Infant mortality decline
- Annual population growth rate with peak annotation

### 5 · Education
- School enrollment by level: primary, secondary, tertiary
- Adult literacy rate over time
- Gender parity analysis — female vs male enrollment (primary & secondary)

### 6 · Trade & exports
- Exports vs imports as % of GDP with trade deficit shading
- Merchandise export composition: food vs manufactures (stacked area)
- Current account balance as % of GDP

### 7 · Digital & infrastructure
- Mobile cellular subscriptions (per 100 people)
- Internet users (% of population)
- Fixed broadband subscriptions
- Access to electricity
- Digital adoption scorecard table: 2010 → 2015 → 2020 → latest

### 8 · Cross-theme correlation analysis
- Correlation heatmap across 12 key indicators
- Scatter plot: GDP per capita vs life expectancy (Preston curve, year-coloured)
- Scatter plot: GDP per capita vs internet adoption

### 9 · Key findings & conclusions
- Written synthesis of insights per theme
- Notable anomalies flagged (HIV/AIDS dip, COVID shock, mobile leap)

---

##  Key findings

###  Economic growth
Kenya's nominal GDP grew **130× from $0.8B (1960) to $107B (2023)**. The 2000s were the strongest decade for growth. The only contraction in recent history came in **2020 (-0.3%)** due to COVID-19, followed by a sharp 7.6% rebound in 2021. Inflation moderated to ~4.5% by 2024 after years above 6%.

###  Health progress
Life expectancy improved from **48.5 to 63.6 years** — remarkable given a notable dip in the 1990s–early 2000s attributable to the HIV/AIDS epidemic. Infant mortality fell from ~120 to under 30 per 1,000 live births. The narrowing birth–death rate gap signals a **demographic transition** underway.

###  Education
Primary enrollment approaches **universal coverage (~98%)**, with gender parity largely achieved at that level. Secondary and tertiary enrollment remain areas of growth opportunity, particularly for girls at secondary level in earlier decades.

###  Trade
Kenya consistently runs a **trade deficit**, with imports exceeding exports as a share of GDP. Food dominates merchandise exports, though manufactured goods are slowly rising as a share — a signal of early industrial diversification.

###  Digital leap
Kenya's **mobile subscription rate of 126 per 100 people** (2024) reflects widespread multi-SIM adoption and is one of Africa's standout digital stories. Internet users grew from near-zero to **38% by 2024**, underpinning the fintech and digital economy revolution (M-Pesa, etc.). Fixed broadband remains low — mobile-first internet access dominates.

---

##  Getting started

### Option A — Google Colab (recommended)

1. Open [Google Colab](https://colab.research.google.com)
2. **File → Upload notebook** → select `kenya_wdi_eda.ipynb`
3. In the **Files panel** (folder icon, left sidebar), upload `API_KEN_DS2_en_csv_v2_5938.csv`
4. **Runtime → Run all**

> All required libraries (pandas, numpy, matplotlib, seaborn) are pre-installed in Colab. No setup needed.

### Option B — Local Jupyter

```bash
# Clone or download the project
git clone https://github.com/your-username/kenya-wdi-eda.git
cd kenya-wdi-eda

# Launch Jupyter
jupyter notebook kenya_wdi_eda.ipynb
```

---

##  Dependencies

| Library | Version | Purpose |
|---|---|---|
| `pandas` | ≥ 1.5 | Data loading & manipulation |
| `numpy` | ≥ 1.23 | Numerical operations |
| `matplotlib` | ≥ 3.6 | Core plotting |
| `seaborn` | ≥ 0.12 | Statistical visualisations & heatmaps |

All of the above are available by default in Google Colab. For local use, install with:

```bash
pip install pandas numpy matplotlib seaborn
```

---

##  Possible extensions

This EDA is designed as a foundation. Here are directions to take it further:

- **Peer comparison** — Download WDI data for Tanzania, Ethiopia, or Ghana and benchmark Kenya against regional peers
- **Poverty & inequality deep-dive** — Explore the `SI.*` indicators: Gini coefficient, poverty headcount ratios, income share by quintile
- **Plotly / interactive charts** — Swap matplotlib for Plotly Express for hover-enabled, zoomable charts
- **ML forecasting** — Use Prophet or ARIMA to project GDP, population, or internet adoption to 2030
- **Sector breakdown** — Add agriculture, manufacturing, and services as % of GDP to show structural transformation
- **Debt analysis** — Explore the `DT.*` indicators to examine external debt trends and debt-service ratios

---

##  Data notes

- **Wide format:** Years are column headers; the notebook reshapes these into time series on the fly via `get_series()`.
- **Missing values:** Early years (pre-1980) have sparser coverage for social indicators. The notebook handles `NaN` gracefully — `dropna()` is applied before plotting.
- **Gross enrollment:** Values above 100% are possible for primary enrollment (reflects over-age students) — this is expected and not a data error.
- **GDP figures:** All in current USD (not inflation-adjusted). For real comparisons across decades, consider using GDP in constant 2015 USD (`NY.GDP.MKTP.KD`).

---

##  License

This project is released under the [MIT License](LICENSE). The underlying dataset is published by the World Bank under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license.

---

<div align="center">

Made with curiosity and data · Kenya 🇰🇪

</div>
