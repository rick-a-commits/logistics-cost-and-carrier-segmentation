# Logistics Cost & Carrier Segmentation

**Data Science Project — Predictive Modeling & Operational Analytics**

This project simulates, analyzes, and models logistics carrier performance for a manufacturing supply chain.
It combines realistic operational KPIs, geospatial data, shipment attributes, CO₂ emissions, and cost modeling.
The goal is to understand cost drivers, segment carriers, and build a model that can estimate shipment pricing.

---

## Project Overview

Modern supply chains rely heavily on external logistics carriers whose performance affects cost, lead time, reliability, and emissions.

This project:

* Generates realistic carrier shipment data (15,000+ rows)
* Cleans and prepares it for analytics
* Explores operational KPIs through EDA
* Segments carriers by performance
* Builds a model that predicts shipment cost
* Highlights insights applicable to business decisions

---

## 📂 Repository Structure

```
├── EDA.ipynb                     # Data exploration & KPI insights
├── carrier_segmentation.ipynb    # Clustering / carrier grouping analysis
├── pricing_mode.ipynb            # ML model predicting cost
├── clean_data.csv                # Cleaned feature dataset ready for modeling
├── carrier_kpi_geographic_15000.csv  # Raw synthetic logistics dataset
├── preprocessor.pkl              # Stored feature transformation pipeline
├── xgb_tuned_model.pkl           # Saved and tuned XGBoost model
└── README.md                     # (this file)
```

---

## 📊 Dataset Summary

**Rows:** 15,000
**Columns:** 20+ including:

| Feature                        | Description                                |
| ------------------------------ | ------------------------------------------ |
| carrier_name                   | Transport/logistics service provider       |
| transport_mode                 | Road, Rail, Air, or Sea                    |
| shipment_weight_kg             | FTL/LTL logic applied                      |
| distance_km                    | Mode-aware geographic distance             |
| cost_usd                       | Mode-weight-distance based cost model      |
| delivery_reliability           | 1 = on time, 0 = delayed                   |
| feedback_reliability           | 1 = feedback given                         |
| lead_time_days                 | Mode- and distance-based transit time      |
| co2_emission_kg                | Estimated based on ton-km emission factors |
| origin/destination_country     | ISO country code                           |
| origin/destination_postal_code | Region-randomized ZIP/postcode             |

---

## Methods & Tools

**Languages / Libraries:**

* Python
* Pandas
* NumPy
* Seaborn / Matplotlib
* Scikit-learn
* XGBoost
* MissingNo
* Pickle for model persistence

---

## 📈 Key Steps

### 1. Data Preparation

* Handled missing & inconsistent values
* Standardized weights, costs, booleans, dates
* Feature engineering:

  * year-month
  * cost per km


---

### 2. Exploratory Data Analysis

* Mode comparison (cost, lead time, emissions)
* Carrier performance ranking
* Outlier detection
* Time-based trends (monthly views)
* Correlation & variable importance
* Visual storytelling using seaborn & matplotlib

Some examples:

* Road = highest volume, mid cost, mid CO₂
* Air = most expensive, fastest, worst emissions
* Sea = cheapest per distance, slowest
* Rail = cost-efficient, low-emissions mid-speed option

---

### 3. Carrier Segmentation

Using clustering & KPI scoring to answer:

* Which carriers are reliable but expensive?
* Which are cheap but inconsistent?


Segments can guide:

* vendor selection
* load allocation
* contract negotiations

---

### 4. Predictive Modeling

Built a machine-learning model to estimate shipment cost based on:

* Mode
* Weight
* Distance
* Carrier
* Emissions

**Model:** XGBoost Regressor
**Artifacts stored:**

* `preprocessor.pkl` (encoding, scaling)
* `xgb_tuned_model.pkl` (trained model)

Metrics and insights included in `pricing_mode.ipynb`.

---

## Business Impact & Use Cases

* **Cost Prediction:** Finance teams can forecast logistics spend
* **Carrier Performance:** Vendor managers can benchmark partners
* **Sustainability:** CO₂ insights support greener lane/carrier choices
* **Operational Efficiency:** Mode-based lead time/cost tradeoffs
* **Strategic Allocation:** Assign shipments to best carriers per KPI

---

## How to Run

1. Clone this repo:

```
git clone https://github.com/rick-a-commits/logistics-cost-and-carrier-segmentation
cd logistics-cost-and-carrier-segmentation
```

2. Install dependencies:

```
pip install -r requirements.txt
```

3. Open and run notebooks in order:

* `EDA.ipynb`
* `carrier_segmentation.ipynb`
* `pricing_model.ipynb`

---

## Next Steps (Future Work)

* Streamlit dashboard for interactive analysis
* Model deployment via FastAPI

---

## ✍️ Author

**Rick (rick-a-commits)**
Data Analyst | Applied Machine Learning | Supply Chain Analytics
GitHub: [https://github.com/rick-a-commits](https://github.com/rick-a-commits)

---

## ⭐ If You Found This Valuable

Give the repository a **star** on GitHub — it helps visibility and signals project quality.

---



