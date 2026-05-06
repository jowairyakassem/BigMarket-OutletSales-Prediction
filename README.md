# Big Mart Outlet Sales Prediction (Regression Task)

---

## Group Members
- Basmala Elkady
- Hany Ziad
- Hoda Mahmoud
- Jana Mamdouh
- Mennatullah Mohamed
- Jowariya Kassem
---

## 1. Introduction
This project addresses a **regression problem** aimed at predicting outlet sales using a structured tabular dataset. The workflow includes data preprocessing, exploratory data analysis, neural network modeling, training, and evaluation.

---

## 2. Problem Definition
The objective is to predict **outlet sales** based on product and store features.

### Final Model Performance:
- **MSE:** 0.3022  
- **MAE:** 0.4216  
- **RMSE:** 0.5497  
- **R² Score:** 0.7189  

---

## 3. Dataset Overview
- Source: Kaggle – Big Mart Sales Dataset  
- Records: ~1559 products across 10 stores  
- Type: CSV file  
- Features: 11 input features + target (sales)

### Features:
- Item_Weight  
- Item_Visibility  
- Item_MRP  
- Outlet_Establishment_Year  
- Item_Identifier_Encoded  
- Item_Fat_Content_Encoded  
- Item_Type_Encoded  
- Outlet_Identifier_Encoded  
- Outlet_Size_Encoded  
- Outlet_Location_Type_Encoded  
- Outlet_Type_Encoded  

---

## 4. Data Preprocessing

### 4.1 Data Cleaning
- Standardized inconsistent categorical values (e.g., LF → Low Fat, reg → Regular)
- Fixed inconsistent outlet size labels

### 4.2 Missing Value Handling
- Item_Weight: Mean imputation per item + global mean fallback  
- Outlet_Size: Mode based on outlet type  

### 4.3 Outlier Handling
- Applied **IQR method**
- Used **clipping** for extreme values

### 4.4 Feature Engineering
- Label Encoding for categorical variables  
- Removed original categorical columns  

### 4.5 Feature Scaling
- StandardScaler applied to all input features  
- Ensures stable neural network training

---

## 5. Exploratory Data Analysis (EDA)
Performed:
- Missing value analysis  
- Duplicate detection  
- Descriptive statistics  
- Categorical feature distribution analysis  

---

## 6. Model Architecture

### Neural Network Structure
- Input Layer: 11 features  
- Hidden Layer 1: 128 neurons (ReLU, He Initialization)  
- Hidden Layer 2: 64 neurons (ReLU)  
- Hidden Layer 3: 32 neurons (ReLU)  
- Output Layer: 1 neuron (Linear activation)

---

## 7. Training Configuration

- Optimizer: Momentum-based Gradient Descent  
- Loss Function: Mean Squared Error (MSE)  
- Epochs: 10,000  
- Batch Size: 42  
- Regularization: L2  

---

## 8. Model Improvements

### Mini-Batch Gradient Descent
- Faster convergence  
- More stable than SGD  

### Momentum Optimization
- Reduces oscillations  
- Accelerates learning in consistent directions  

### Regularization (L2)
- Prevents overfitting  
- Stabilizes weight updates  

---

## 9. Results

### Optimized Model Performance:
- **Test MSE:** 0.3022  
- **Test MAE:** 0.4216  
- **Test RMSE:** 0.5497  
- **Test R² Score:** 0.7189  

---

## 10. Observations & Conclusions

- Performance improved significantly with **Momentum + L2 + Mini-Batch training**
- Standardization was critical for stable neural network convergence
- The model successfully captures nonlinear relationships in sales data
- Final R² score (~0.71) indicates strong predictive capability for a regression task

---

## 11. Tools & Technologies
- Python  
- NumPy / Pandas  
- Scikit-learn  
- Neural Networks (from scratch / framework used)  
- Matplotlib / Visualization tools  

---

## 12. References
- Kaggle Dataset: Big Mart Sales Prediction  
- Neural Networks Lecture Material (AI231 Course)  
