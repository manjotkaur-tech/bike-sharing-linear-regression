# bike-sharing-linear-regression
# 🚲 Bike Sharing Demand Prediction (Linear Regression)

This project predicts the **daily bike rental count** using weather, seasonal, and calendar information.  
It is based on the **Bike Sharing Dataset (`day.csv`)** and demonstrates the complete process of **building and evaluating a linear regression model**.

---

## 📊 Project Workflow

### 1. Data Exploration
- Loaded and inspected dataset (730 rows × 16 columns).
- Checked for missing values (none found).
- Explored variable distributions and correlations using:
  - Heatmaps
  - Pairplots
  - Boxplots
  - Scatterplots

### 2. Data Preparation
- Dropped irrelevant columns: `instant`, `atemp`, `casual`, `registered`.
- Converted categorical variables (`season`, `month`, `weekday`, `weathersit`) into **dummy variables**.
- Applied **MinMax Scaling** on numeric features.

### 3. Model Building
- Split dataset into **70% training** and **30% testing**.
- Used **Recursive Feature Elimination (RFE)** to select key predictors.
- Removed multicollinearity using **Variance Inflation Factor (VIF)**.
- Built multiple OLS regression models step by step to refine predictors.

### 4. Final Model
- **Selected Features**:  
  `Dec, Jan, Sep, Light Snow, Mist + Cloudy, spring, summer, winter, yr, temp`
- **Train R²**: ~0.818 (Adjusted ~0.814)  
- **Test R²**: ~0.81 (Adjusted ~0.79)

### 5. Evaluation
- Plotted predicted vs actual values.
- Checked residuals and error distribution.
- Confirmed good generalization of the model.

---

## 🔑 Key Insights
- **Temperature** has the strongest positive effect on rentals.
- **Snow, cloudy weather, humidity, and windspeed** reduce rentals.
- **2019 saw more rentals than 2018** (positive effect of `yr`).
- Certain months (Jan, Dec, Nov) show lower demand.

---

## 🛠️ Technologies Used
- Python
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn
- Statsmodels

---

## 📌 How to Run
1. Clone this repo  
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
