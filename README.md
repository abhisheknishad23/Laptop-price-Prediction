# Laptop Price Predictor

A End-to-End Machine Learning project that predicts the price of a laptop based on its configuration (Brand, Type, RAM, CPU, GPU, OS, Weight, Touchscreen, IPS Display, and PPI).


---

## 📌 Project Overview
Buying a laptop can be overwhelming with so many configurations available. This project aims to build a web application where users can input specific laptop specifications and get an accurate estimated market price in Indian Rupees (₹).

The dataset used contains specifications of **1303 laptops**, which underwent rigorous Data Cleaning, Exploratory Data Analysis (EDA), and Feature Engineering.

---

## 🛠️ Key Technical Features

### 1. Feature Engineering & Preprocessing
* **Target Variable Transformation:** Since the `Price` column was highly right-skewed, applied **Log Transformation (`np.log`)** to improve model convergence and performance.
* **Screen Resolution Handling:** Extracted `Touchscreen` and `Ips` display flags, calculated the **Pixel Density (PPI - Pixels Per Inch)** using the formula:
    $$PPI = \frac{\sqrt{X_{res}^2 + Y_{res}^2}}{Inches}$$
* **CPU & GPU Categorization:** Cleaned complex string names to group processors into core brands (Intel Core i3/i5/i7, AMD, Other Intel) and GPU categories (Intel, Nvidia, AMD).
* **Storage Decomposition:** Handled combined storage strings (e.g., "128GB SSD + 1TB HDD") to extract exact numeric capacities for `SSD` and `HDD` in GBs.
* **Categorical Encoding:** Built a robust data preprocessing pipeline using Scikit-Learn's `ColumnTransformer` and `OneHotEncoder`.

### 2. Machine Learning Pipeline & Stacking
Tried multiple regression algorithms (Linear Regression, Ridge, Decision Tree, Random Forest, XGBoost) and finally achieved the highest accuracy using an ensemble approach:
* **Base Estimators:** Random Forest Regressor, Gradient Boosting Regressor, and XGBoost Regressor.
* **Final Meta-Estimator:** Ridge Regression via Scikit-Learn's **`StackingRegressor`**.
* **Performance Metrics:** Achieved an **$R^2$ Score of ~87.8%** with a significantly low Mean Absolute Error (MAE).

---

##  Tech Stack Used
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn
* **Deployment & UI:** Streamlit 
* **Environment:** Jupyter Notebook / PyCharm

---

## 🏃‍♂️ How to Run Locally

1. **Clone the repository:**
   ```bash
   
