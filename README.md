# 💻 **Laptop Price Prediction — Machine Learning Project**

## 📘 *MBA IT — Data Analytics Project*

### 👨‍🎓 **Student**

- **Shlok Tilokani** (ID: 24030141072)

---

![Laptop Price Prediction](res/video.gif)

---

## 🔍 **Project Overview**

This project aims to build a machine learning model that predicts **laptop prices** based on specifications such as brand, processor, RAM, storage, ratings, etc.

The workflow includes:

- Dataset exploration (EDA)
- Preprocessing & feature engineering
- Model training using **Linear Regression**
- Evaluation using statistical metrics
- Visualization of model performance
- Testing with real samples

---

## 🌱 **Nature of Dataset**

According to *main.pdf* and *documentation.pdf*, the dataset contains **823 laptop entries** with **19 columns**. fileciteturn1file0

### **🔹 Features Include:**

- `brand`
- `processor_brand`
- `processor_name`
- `processor_gnrtn`
- `ram_gb`
- `ram_type`
- `ssd`
- `hdd`
- `os`
- `os_bit`
- `graphic_card_gb`
- `weight`
- `warranty`
- `rating`
- `Number of Ratings`
- `Number of Reviews`

### **🎯 Target Variable:**

- `Price`

### **Dataset Properties:**

- Total rows: **823**, Columns: **19**
- No missing values observed in dataset sample
- Combination of categorical + numerical features

---

## ⚙️ **Project Workflow**

### **1️⃣ Import Libraries**

Libraries used:

- `pandas`, `numpy` → Data handling
- `matplotlib`, `seaborn` → Visualization
- `scikit-learn` → Modeling & evaluation

---

### **2️⃣ Load the Dataset**

```python
df = pd.read_csv('laptopPrice.csv')
df.head()
```

Sample rows in *main.pdf* show first few entries with brand, RAM, OS, ratings, etc. fileciteturn1file0

---

### **3️⃣ Exploratory Data Analysis (EDA)**

The following were analyzed: fileciteturn1file0

- Dataset shape → `(823, 19)`
- Data types
- Missing values (none detected)
- Summary statistics of numerical columns
- Correlation matrix
- Heatmap showing relationships between `Price`, `Number of Ratings`, and `Number of Reviews`

### **📊 Key EDA Insights**

- `Number of Ratings` and `Number of Reviews` are strongly correlated.
- Linear patterns observed for several features → suitable for Linear Regression.
- Wide variance in `Price` (min ~₹20k, max ~₹4.4L), contributing to high MSE.

A sample correlation heatmap is shown in *main.pdf* (page 3). fileciteturn1file0

---

### **4️⃣ Data Preprocessing**

From *documentation.pdf* steps:
 fileciteturn1file1

- Removed duplicates
- Handled missing values
- Converted datatypes where required
- Applied **one-hot encoding** for categorical columns
- Performed **train-test split** → 80% training, 20% testing
- Feature scaling not required for Linear Regression

Code sample:

```python
X = df.drop('Price', axis=1)
y = df['Price']
X = pd.get_dummies(X, drop_first=True)
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

---

### **5️⃣ Model Building — Linear Regression**

Linear Regression was selected for:
 fileciteturn1file1

- Simplicity and interpretability
- Baseline benchmark
- Fast computation
- Works well with linear relationships

### **Model Code:**

```python
model = LinearRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)
```

---

### **6️⃣ Model Evaluation**

The following metrics were calculated: fileciteturn1file1

### **📊 Evaluation Metrics**

| Metric | Value | Interpretation |
|--------|--------|----------------|
| **Mean Squared Error (MSE)** | 576,410,115.15 | High due to large price range |
| **R² Score** | 0.7042 | Model explains **70%** variance |
| **Approx Accuracy** | 81.84% | Based on MAPE |

### **📝 Interpretation**

- Good baseline performance
- Some prediction errors due to nonlinear relationships
- Price-sensitive features (e.g., high-end processors) cause larger error ranges

---

### **7️⃣ Visualization — Actual vs Predicted**

Graphs included in *main.pdf*:
 fileciteturn1file0

- **Line Plot** → Overlapped actual vs predicted prices across test samples
- **Scatter Plot** → Shows linear trend between predicted and actual prices

These plots confirm:

- Predictions follow real price trends
- Some deviations for extremely high-priced laptops

---

## 🧪 **8️⃣ Test Case Results**

Sample of 5 test cases from *documentation.pdf*: fileciteturn1file1

| Actual Price | Predicted Price | Abs Error | Absolute % Error |
|--------------|----------------|-----------|-------------------|
| 33,690 | 33,809 | 119 | 0.35% |
| 86,990 | 72,695 | 14,294 | 16.43% |
| 39,490 | 41,486 | 1,996 | 5.06% |
| 63,990 | 79,625 | 15,635 | 24.43% |
| 134,990 | 139,333 | 4,343 | 3.22% |

### **Insights from Test Cases**

- Very accurate predictions for mid-range laptops
- Higher errors for outlier/rare specifications
- Overall model accuracy is **~82%**

---

## 💡 **Project Insights**

- Linear Regression works well for baseline prediction of laptop prices
- Dataset is clean and well-structured
- Categorical encoding increases model reliability
- Strong correlations among rating-based features

---

## 🏁 **Conclusion**

The model achieved:

- **R² Score:** 0.7042
- **Approx Accuracy:** 81.8%

This confirms that **Linear Regression successfully predicts laptop prices** with fairly good accuracy. It provides:

- Interpretability
- Fast computation
- Reliable baseline for comparison with advanced models

---

## 🚀 **Future Work**

- Train advanced models: Random Forest, XGBoost, Neural Networks
- Add new features: brand popularity, market trends
- Hyperparameter tuning
- Deploy model as a **web app** with real-time prediction

---

### ⭐ **Thank You!**

Feel free to ⭐ star the repo if this project helped you!
