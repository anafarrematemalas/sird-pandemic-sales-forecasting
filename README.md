# 💊 SIRD Model Integration & Sales Prediction for Pandemic Supply Management

Final Degree Project (TFG) — Mathematical Engineering, **Universidad Francisco de Vitoria** (July 2024).

**Author:** Ana Farré Matemalas
**Supervisor:** Carlos Emilio Rabazo

## 📌 Abstract

This project addresses supply preparedness and management during a pandemic. It combines epidemiological modeling with sales forecasting: the **SIRD model** (Susceptible–Infected–Recovered–Deceased) is used to simulate disease spread, while several **predictive models** (regression, time series, and machine learning) are used to forecast pharmacy medicine sales. The work also discusses the ethical implications of data management and decision-making during a public health crisis.

**Keywords:** Prediction, Database, Pharmacy, Optimization, SIRD Model, Inventory

## 🎯 Objectives

- Simulate the spread of a disease using the SIRD epidemiological model.
- Forecast medicine sales during a pandemic using predictive models.
- Combine both approaches to support inventory and supply-chain decisions in pharmacies during health crises.
- Evaluate model accuracy and apply the trained models to a simulated future pandemic scenario.

## 🗂️ Repository structure

```
├── PFG.pdf        # Full written report (Spanish)
├── DEFENSA PFG.pptx                   # Defense presentation slides
├── notebooks/
│   ├── creacion_un_solo_csv-2.ipynb          # Data consolidation into a single dataset
│   ├── analisis_exploratorio-2.ipynb         # Exploratory data analysis
│   ├── PFG- prediccion pandemia.ipynb        # SIRD model & pandemic simulation
│   └── modelos_predictivos-2.ipynb           # Predictive / ML models for sales forecasting
├── datasets iniciales/                # Raw source data (pharmacy sales & product tables)
│   ├── venta(2020/2021/2022).csv
│   ├── lineaventa(2020/2021/2022).csv
│   ├── Articu.csv
│   └── FamArticu.csv
├── datasets limpios/                  # Cleaned / processed datasets used in the notebooks
│   ├── ventas.csv.zip                 # Combined sales data (compressed, see note below)
│   ├── evolucion_pandemia.csv         # COVID-19 case evolution data (Spain, by province)
│   └── datos_combinados_por_medicamento.csv  # Sales + pandemic data merged by medicine
└── screenshots/                       # Result plots and figures used in the report
```

## 🧪 Methodology & tools

- **SQL Server** — original database exploration and data extraction.
- **Excel** — intermediate conversion to CSV.
- **Python (Google Colab)** — data cleaning, exploratory analysis, SIRD modeling, and predictive modeling.

Main Python libraries used: `pandas`, `numpy`, `scipy.stats`, `matplotlib`, `seaborn`, `statsmodels`, `scikit-learn` (Linear/Polynomial Regression, Random Forest, Gradient Boosting), `keras` (neural networks), `statsmodels.ARIMA` (time series).

## 📊 Datasets

| File | Description |
|---|---|
| `venta(YYYY).csv` / `lineaventa(YYYY).csv` | Raw pharmacy sales transactions and line items (2020–2022) |
| `Articu.csv` / `FamArticu.csv` | Product and product-family reference tables |
| `evolucion_pandemia.csv` | Daily COVID-19 case evolution in Spain by province, sex, and age group |
| `datos_combinados_por_medicamento.csv` | Combined dataset: daily sales per medicine + pandemic indicators |
| `ventas.csv.zip` | Full cleaned sales dataset (combined from all years) |

> ⚠️ **Note on `ventas.csv.zip`:** the cleaned sales dataset is ~150 MB uncompressed, above GitHub's 100 MB file limit, so it is stored zip-compressed (~37 MB) in this repository. It can be loaded directly with pandas without manual extraction:
> ```python
> import pandas as pd
> df = pd.read_csv("datasets limpios/ventas.csv.zip")
> ```

## 📈 Results

The project compares several regression and machine learning models to select the one with the best sales-prediction accuracy, then applies the trained model together with SIRD-simulated pandemic waves to estimate medicine demand under a new hypothetical pandemic scenario. Full results, figures, and conclusions are detailed in the written report (`PFG.pdf`).

## ⚖️ Ethical considerations

The project also discusses the ethical implications of using health and sales data for forecasting and decision-making during a public health crisis, including data privacy and the social impact of supply-management decisions.

---

*Academic Final Degree Project — Mathematical Engineering, Universidad Francisco de Vitoria, 2024.*
