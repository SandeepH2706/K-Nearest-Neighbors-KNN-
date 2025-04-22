# 🔍 K-Nearest Neighbors (KNN) Algorithm

**K-Nearest Neighbors (KNN)** is a simple, versatile, and widely used **supervised machine learning algorithm** used for both **classification** and **regression** tasks. However, it is **more commonly used for classification**.

KNN is a **non-parametric**, **instance-based (lazy learning)** algorithm:
- It **makes no assumptions** about the underlying data distribution.
- It **does not learn** a discriminative function from the training data.
- Instead, it **memorizes the dataset** and makes predictions based on the **'k' closest training examples** in the feature space.

---

## ⚙️ How It Works

1. **Choose** the number of neighbors \( k \).
2. **Calculate** the distance between the new input and all training samples (commonly **Euclidean distance**).
3. **Sort** the distances and find the **k nearest neighbors**.
4. **Make predictions**:
   - **Classification**: Use **majority voting** among the k neighbors.
   - **Regression**: Take the **average** (or **weighted average**) of the k neighbors’ values.

---

## 🔑 Key Parameters

- **`n_neighbors`**: Number of neighbors to consider (**k**).  
  → Higher k reduces noise but may blur class boundaries.

- **`weights`**:  
  → `'uniform'`: All neighbors have equal weight  
  → `'distance'`: Closer neighbors have more influence

- **`algorithm`**:  
  → `'auto'`, `'ball_tree'`, `'kd_tree'`, or `'brute'`  
  → Specifies the method used to compute nearest neighbors

- **`p`**:  
  → Power parameter for **Minkowski distance**  
  → `p=1` → Manhattan distance  
  → `p=2` → Euclidean distance

- **`metric`**:  
  → Distance metric to use (default: `'minkowski'`)  
  → Can also define **custom metrics**

---

## 📈 Evaluating KNN Performance

### Classification Metrics
- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **Confusion Matrix**
- **ROC-AUC Curve**

### Regression Metrics
- **Mean Squared Error (MSE)**
- **Mean Absolute Error (MAE)**
- **R² Score** (Coefficient of Determination)

---

## 🔁 Cross-Validation

Use **K-Fold Cross-Validation** to:
- Select the **optimal value of k**
- Avoid **overfitting** and **underfitting**

---

## 🧠 Choosing the Best `k`

- **Small `k`** → More sensitive to noise → **High variance**
- **Large `k`** → Smoother decision boundary → **High bias**
- Use **Grid Search** with **Cross-Validation** to find the **optimal k**

---

## ⚠️ Limitations

- ⚡ **Slow at prediction time** for large datasets (since it scans all data)
- ❗ **Sensitive** to irrelevant or redundant features
- 📉 Performance **degrades with high-dimensional data** (curse of dimensionality)
- 🔧 **Requires feature scaling** (e.g., `StandardScaler` or `MinMaxScaler`)

