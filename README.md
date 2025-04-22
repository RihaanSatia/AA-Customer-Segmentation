
# Customer Segmentation for Airline Revenue Optimization

This project applies **data preprocessing, exploratory data analysis (EDA)**, and a customized **Weighted K-Means clustering approach** to identify customer segments based on **willingness to pay (WTP)** and **booking behavior**. The primary goal is to enable **data-driven revenue management strategies** for airlines, particularly American Airlines.

---

## 📁 Notebooks

### 1. `Preprocessing and EDA.ipynb`
This notebook handles the full data pipeline before modeling, including:

- **Data Cleaning & Inspection**
  - Handling missing values and anomalies (e.g., impossible booking windows).
  - Standardizing values like `CHANNEL` and replacing unknowns.

- **Feature Engineering**
  - Creation of behavioral and contextual features:
    - `ADVANCED_PURCHASE`, `ROUNDTRIP`, `NONSTOP`, `REVENUE_PER_PERSON`, `TRAVEL_TYPE`, etc.
  - Custom logic to detect **holiday travel**, **weekend patterns**, **booking windows**, and **cumulative bookings**.

- **Exploratory Data Analysis**
  - Correlation matrix, revenue by channel/type, booking trends.
  - Top origin-destination pairs, travel seasonality, revenue per booking window.

- **Data Selection**
  - Focus narrowed to **leisure travelers**, excluding business and bleisure categories.

> ✅ Processed dataset is stored as CSV for modeling purposes.
> Dataset is not available due to NDA restrictions.

---

### 2. `Weighted K-Means2.ipynb`
This notebook applies **custom clustering** based on WTP indicators and behavioral features:

- **Additional Feature Engineering** (focused on WTP proxies):
  - `Revenue_AP_Ratio`: Urgency vs. spending behavior.
  - `Distance_Adjusted_Revenue`: Paying a premium relative to peers in the same distance band.
  - `Cumulative_Advance_Purchase_Ratio`: Booking behavior compared to others.
  - `Channel_RPM_Ratio`: Price per mile per channel.

- **Data Preparation**
  - Encoding travel characteristics: `WEEKEND_ARRIVAL`, `HOLIDAY_RETURN`, `ROUNDTRIP`, etc.

- **Weighted K-Means Clustering**
  - Clusters analyzed for key differences in behavior, travel purpose, and revenue contribution.
  - Emphasis on interpreting segments to drive pricing strategy varyingness in Willingness to Pay

---

## 🔍 Objectives

- Understand and segment airline passengers using **behavioral clustering**.
- Identify features that signal **high willingness to pay**.
- Improve **targeted marketing** and **dynamic pricing** strategies.

---

## 🛠️ Technologies Used

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn for clustering
- Jupyter Notebook
- U.S. Holidays API
- Public aviation data for distance mapping

---

## 📌 Future Enhancements

- Model validation with external ticket pricing data.
- Integration of PCA/GMM for visualizing high-dimensional clustering.
- Deployment as a dashboard.
