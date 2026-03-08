
# 🧬 Breast Cancer Detection using Deep Learning

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

A **Deep Learning based classification system** that predicts whether a breast tumor is **malignant (cancerous)** or **benign (non-cancerous)** using medical features from the **Breast Cancer Wisconsin Dataset**.

The model is implemented using **TensorFlow/Keras** and trained on **30 diagnostic features extracted from digitized breast tissue images**.

---

# 📌 Project Overview

Breast cancer is one of the most common cancers worldwide. Early detection significantly improves survival rates.

This project builds an **AI-based medical classification system** that learns patterns from tumor data and predicts cancer presence.

The model follows a complete **machine learning pipeline** including:

* Data preprocessing
* Feature scaling
* Neural network training
* Model evaluation
* Tumor classification

---

# 🏗 Project Architecture

```
Dataset (Breast Cancer Wisconsin)
            │
            ▼
     Data Preprocessing
            │
            ▼
  Feature Standardization
            │
            ▼
      Train-Test Split
            │
            ▼
   Neural Network Model
            │
            ▼
      Model Training
            │
            ▼
      Model Evaluation
            │
            ▼
        Prediction
```

---

# 📊 Dataset

The project uses the **Breast Cancer Wisconsin Diagnostic Dataset** available in **Scikit-Learn**.

| Property           | Value                     |
| ------------------ | ------------------------- |
| Total Samples      | 569                       |
| Number of Features | 30                        |
| Classes            | 2                         |
| Class Labels       | Malignant (0), Benign (1) |

### Example Features

* radius_mean
* texture_mean
* perimeter_mean
* area_mean
* smoothness_mean
* concavity_mean
* symmetry_mean

These features represent **cell nucleus characteristics obtained from biopsy images**.

---

# ⚙️ Technologies Used

| Technology               | Purpose                 |
| ------------------------ | ----------------------- |
| Python                   | Programming language    |
| TensorFlow / Keras       | Deep learning framework |
| Scikit-Learn             | Dataset & preprocessing |
| NumPy                    | Numerical computation   |
| Pandas                   | Data handling           |
| Matplotlib               | Data visualization      |
| Jupyter Notebook / Colab | Model development       |

---

# 📂 Project Structure

```
BREAST-CANCER-DETECTION
│
├── BREAST_CANCER_DETECTION.ipynb
├── README.md
```

---

# 🔬 Implementation

## 1️⃣ Data Loading

The dataset is loaded using Scikit-Learn.

```python
from sklearn.datasets import load_breast_cancer
breast_cancer_dataset = load_breast_cancer()
```

The dataset is converted into a **Pandas DataFrame** for easier manipulation.

---

# 2️⃣ Data Preprocessing

Features and labels are separated.

```python
X = data_frame.drop(columns='label', axis=1)
Y = data_frame['label']
```

Where

* **X** → feature matrix
* **Y** → classification labels

---

# 3️⃣ Train-Test Split

The dataset is divided into training and testing sets.

```python
train_test_split(X, Y, test_size=0.3, random_state=2)
```

| Dataset       | Portion |
| ------------- | ------- |
| Training Data | 70%     |
| Testing Data  | 30%     |

---

# 4️⃣ Feature Scaling

Standardization is applied using **StandardScaler**.

```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
```

Formula used:

[
X_{scaled} = \frac{X - \mu}{\sigma}
]

This ensures all features have **equal scale for better model learning**.

---

# 🧠 Neural Network Architecture

The deep learning model is built using **Keras Sequential API**.

```python
model = keras.Sequential([
keras.layers.Flatten(input_shape=(30,)),
keras.layers.Dense(20, activation='relu'),
keras.layers.Dense(2, activation='sigmoid')
])
```

### Layer Details

| Layer              | Description                       |
| ------------------ | --------------------------------- |
| Flatten            | Converts features to 1D vector    |
| Dense (20 neurons) | Hidden layer with ReLU activation |
| Dense (2 neurons)  | Output layer for classification   |

---

# ⚡ Model Compilation

```python
model.compile(
optimizer='adam',
loss='sparse_categorical_crossentropy',
metrics=['accuracy']
)
```

| Component          | Purpose                 |
| ------------------ | ----------------------- |
| Adam               | Efficient optimizer     |
| Cross-Entropy Loss | Used for classification |
| Accuracy           | Performance metric      |

---

# 🏋️ Model Training

The model is trained for **30 epochs**.

```python
model.fit(X_train_std, Y_train, validation_split=0.1, epochs=30)
```

During training the model learns **patterns between medical features and tumor type**.

---

# 📈 Training Performance

### Accuracy vs Epoch

*(Add training accuracy graph screenshot here)*

### Loss vs Epoch

*(Add training loss graph screenshot here)*

These plots help visualize **model learning progress**.

---

# 📊 Model Evaluation

The model is evaluated using the test dataset.

```python
loss, accuracy = model.evaluate(X_test_std, Y_test)
```

The accuracy indicates how well the model predicts **previously unseen data**.

---

# 🔮 Prediction Example

Example prediction from the trained model:

```python
prediction = model.predict(X_test_std)
np.argmax(prediction)
```

| Output | Meaning   |
| ------ | --------- |
| 0      | Malignant |
| 1      | Benign    |

---

# 🎯 Results

The deep learning model successfully predicts breast cancer using diagnostic features.

Typical performance:

| Metric   | Result  |
| -------- | ------- |
| Accuracy | ~95–97% |
| Loss     | Low     |

The model demonstrates **strong classification performance** on the dataset.

---

# 📚 Learning Outcomes

Through this project:

* Built a **complete deep learning pipeline**
* Implemented **data preprocessing and feature scaling**
* Designed a **Neural Network classifier**
* Evaluated models using test data
* Converted probabilities into classification labels

---

# 🔮 Future Improvements

Possible improvements:

* Hyperparameter tuning
* Cross-validation
* Deeper neural network architectures
* Model deployment using **Flask / FastAPI**
* Web interface for real-time predictions

---

# 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create a new branch
3. Commit changes
4. Submit a pull request

---

# 📜 License

This project is licensed under the **MIT License**.


💡 If you want, I can also show you **3 GitHub tricks that will instantly make your profile look like a strong ML developer profile** (this helps a lot for **internships and research positions**).
