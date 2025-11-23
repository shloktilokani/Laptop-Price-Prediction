# 🖥️ **Laptop Price Prediction — Machine Learning Project**

## 📌 **Project Overview**

This project aims to **predict laptop prices** based on various hardware and brand specifications using **Linear Regression**. The goal is to build an interpretable baseline model that identifies how different laptop features influence pricing.

---

## 🧾 **Nature of the Dataset**

- Contains **823 rows** and **19 columns** of laptop specifications.
- Includes **categorical** (brand, processor name, OS, etc.) and **numerical** (RAM, SSD, weight, ratings, etc.) features.
- **Target Variable:** `Price`
- **Features Include:**
  - Brand
  - Processor brand, processor name, generation
  - RAM size & type
  - SSD & HDD storage
  - Operating System & OS bit
  - GPU size
  - Weight
  - Warranty
  - Number of ratings & reviews

---

## 🧪 **Steps Performed in the Project**

### **1️⃣ Data Loading**

- Loaded dataset using **Pandas**.
- Viewed sample rows to understand structure.

### **2️⃣ Exploratory Data Analysis (EDA)**

- Checked dataset **shape**, **info**, and **data types**.
- Verified **missing values** — none found.
- Generated **summary statistics** for numerical columns.
- Created **correlation heatmap** to observe relationships:
  - Price showed weak correlation with ratings/reviews.
  - Some categorical columns likely influence pricing non-linearly.

### **3️⃣ Data Preprocessing**

- Selected independent features (X) and target variable (y = Price).
- Encoded categorical variables using **One-Hot Encoding**.
- Split data into **80% training** and **20% testing**.

### **4️⃣ Model Building**

- Used **Linear Regression** as baseline model.
- Trained model on training data.
- Generated predictions on test data.

### **5️⃣ Model Evaluation**

Used the following metrics:

- **Mean Squared Error (MSE):** 576,410,115.15
- **R² Score:** 0.7042
- **Approx Accuracy:** ~81.8%

### **6️⃣ Visualizations**

- **Line Graph:** Actual vs Predicted prices for test set.
- **Scatter Plot:** Correlation between actual & predicted prices.
  - Majority of points lie near diagonal → good prediction consistency.

### **7️⃣ Test Cases (Random Samples)**

| Actual Price | Predicted Price |
|-------------:|----------------:|
| 33690        | 33809           |
| 86990        | 72695           |
| 39490        | 41486           |
| 63990        | 79625           |
| 134990       | 139333          |

---

## 🧠 **Insights Gained**

- Model performs reasonably well with **~82% accuracy**.
- Price is **weakly correlated** with ratings & reviews → these are not strong predictors.
- Categorical features like **brand**, **processor type**, **RAM**, and **storage** likely carry significant influence.
- Linear Regression captures base patterns but misses complex nonlinear interactions.

---

## ⚙️ **Model Parameters & Settings**

- **Algorithm:** Linear Regression
- **Train-Test Split:** 80/20 (random_state = 42)
- **Encoding Method:** One-Hot Encoding
- **Scaling:** Not used (optional for LR)
- **Evaluation Metrics:** MSE, R², MAPE-derived accuracy

---

## 📌 **Conclusion**

- Linear Regression provides a good baseline with **decent accuracy (~82%)**.
- The model is simple, interpretable, and effective for initial price prediction tasks.
- Some prediction errors occur due to:
  - Nonlinear relationships
  - Underrepresented laptop configurations
  - Missing hidden factors (brand reputation, latest market trends)

---

## 🚀 **Future Scope**

- Train more complex models:
  - Random Forest
  - XGBoost
  - Neural Networks
- Add additional features:
  - Release year
  - GPU model
  - Display type
- Deploy model via **Flask/Streamlit web app** for real-time price prediction.

---

## 🙏 **Acknowledgement**

This project is part of the **MBA-IT (Data Analytics)** coursework and demonstrates practical application of regression models in real-world pricing problems.

---

### ⭐ **Thank You for Reading!**

Feel free to contribute, improve, or suggest ideas for this project.
