# ✈️ Flight Delay Insights and ML Prediction

This project was developed for a DataCamp competition focused on analyzing U.S. flight delays. It includes a full data science pipeline: data cleaning, exploratory analysis, visualization, and a machine learning model to predict delays of 15 minutes or more.

---

## 📊 Objectives

1. Analyze delay patterns across airlines, time periods, and airports
2. Visualize trends in punctuality by month and hour
3. Compare airport performance
4. Predict whether a flight will be delayed by 15+ minutes
5. Identify the most influential factors behind delays

---

## 📁 Dataset

Due to GitHub's file size limits, the original dataset is not included in this repository.

You can download the data from its original source on Kaggle:

- **Flights dataset:** [Flight Delays Dataset – Kaggle](https://www.kaggle.com/datasets/mahoora00135/flights)

Once downloaded, upload the following two files to your working environment:

- `flights.csv`: Includes departure/arrival times, delays, distance, carrier, etc.
- `airlines_carrier_codes.csv`: Maps airline codes to full airline names

---

## 🧼 Data Cleaning

We identified missing values in key columns:

- `dep_delay`, `arr_delay`, `air_time` — essential for modeling
- `dep_time`, `arr_time` — used for context
- `tailnum` — dropped (not useful here)

We removed rows with missing values and flights with extreme delays (`dep_delay > 1000`).  
✅ **Cleaned dataset: 327,341 valid flights**

---

## 📊 Exploratory Data Analysis (EDA)

We explored key delay patterns using grouped metrics and visualizations:

- 📈 **By airline**: Frontier and ExpressJet had highest average departure delays
- 📆 **By month**: Delays peak in July and June
- 🕒 **By hour**: Late afternoon/evening flights (4–9 PM) had more delays
- 🛫 **By airport**: EWR and JFK show the most frequent disruptions

Visuals include bar plots, line plots, and boxplots to uncover trends.

---

## 🤖 Predictive Modeling

We trained a **Random Forest Classifier** to predict whether a flight will be delayed 15+ minutes.

- **Target variable**: `delay_15min` (1 = delayed ≥15 min, 0 = on time)
- **Features used**: `month`, `hour`, `distance`, `air_time`, `carrier`

### 🔍 Results:

- **Accuracy**: 74%
- **Precision (delays)**: 36%
- **Recall (delays)**: 29%

> ⚠️ Class imbalance and lack of external factors (e.g., weather) reduced recall. Future iterations could improve performance with more context-rich data.

---

## 🔎 Feature Importance (Optional 2)

Using the Random Forest model, we identified top predictors of delay:

1. `hour` — Time of day
2. `month` — Seasonal patterns
3. `distance` — Longer routes had distinct patterns
4. `air_time` — Related to disruption exposure

These insights suggest that time, season, and route complexity are strong indicators of potential delays.

---

## 🛠️ Tools & Libraries

- Python, Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn (Random Forest, evaluation metrics)
- Google Colab + GitHub

---

## 👩‍💻 Author

**Maria Almeida**  
Industrial Engineer | Data Enthusiast | Aspiring ML Engineer  


---

## 🚀 Status

✅ Fully completed and submitted for the DataCamp community competition  
✅ Cleaned, analyzed, modeled and visualized — ready for portfolio!
