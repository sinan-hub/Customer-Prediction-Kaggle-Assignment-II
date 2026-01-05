# 🏨 Hotel Booking Cancellation Prediction – Kaggle Assignment

## 📌 Problem Statement
The objective of this project is to build a **machine learning classification model** that predicts whether a customer will **cancel a hotel booking or not** based on booking details, customer attributes, and stay information.

The problem is formulated as a **binary classification task**, where:
- `1` → Booking Cancelled  
- `0` → Booking Not Cancelled  

This assignment is implemented and evaluated using the **Kaggle platform**.

---

## 📂 Dataset Description
The dataset consists of the following files:

- `train.csv` – Training dataset containing features and the target variable  
- `test.csv` – Test dataset with hidden target values  
- `sample_submission.csv` – Sample submission format for Kaggle  

---

## 🧾 Feature Description

| Column Name | Description |
|------------|------------|
| `id` | Unique identifier |
| `adults` | Number of adults |
| `children` | Number of children |
| `weekends` | Number of weekend days |
| `weekdays` | Number of weekday days |
| `meal_type` | Meal plan chosen |
| `room_type` | Room type selected |
| `arrival` | Arrival date |
| `lead_time` | Days between booking and arrival |
| `segment` | Booking segment |
| `repeat` | Whether customer is a repeat guest |
| `price` | Average price per room |
| `requests` | Number of special requests |
| `booking_status` | Target variable (1 = Cancelled, 0 = Not Cancelled) |

---

## 🔧 Libraries Used
The following Python libraries are used in the notebook:

- **Pandas & NumPy** – Data handling and numerical operations  
- **Matplotlib & Seaborn** – Exploratory data analysis and visualization  
- **Scikit-learn** – Preprocessing, modeling, and evaluation  
- **XGBoost / LightGBM** – Gradient boosting classification models  

---

## 🔍 Exploratory Data Analysis (EDA)
EDA is performed to understand customer behavior and booking patterns:

- Dataset shape and basic statistics
- Distribution of booking cancellations
- Analysis of numerical features such as price, lead time, and stay duration
- Cancellation trends based on room type, meal type, and booking segment
- Checking for missing values and class imbalance

---

## 🧹 Data Preprocessing

### 1. Handling Missing Values
- Missing numerical values are filled using median or mean
- Missing categorical values are filled using mode

### 2. Feature Engineering
- Arrival date is converted into useful components (month, day)
- Total stay duration calculated using weekdays and weekends
- Removal of unnecessary or highly correlated features

### 3. Encoding Categorical Variables
- Categorical columns (`meal_type`, `room_type`, `segment`) are encoded using:
  - Label Encoding
  - One-Hot Encoding where required

### 4. Feature Scaling
- Numerical features are scaled using **StandardScaler** for better model convergence

---

## 🤖 Machine Learning Models Used
Multiple classification models are trained and compared:

- **Logistic Regression**
- **Decision Tree Classifier**
- **Random Forest Classifier**
- **Gradient Boosting Classifier**
- **XGBoost / LightGBM Classifier**

Each model is evaluated on a validation split to identify the best-performing algorithm.

---

## 📏 Model Evaluation
The primary evaluation metric used is:

- **Accuracy Score**

Additional metrics such as **precision**, **recall**, and **confusion matrix** are analyzed to ensure balanced performance.

---

## 🔧 Hyperparameter Tuning
For ensemble models (Random Forest, XGBoost, LightGBM):

- Hyperparameters are tuned using **GridSearchCV**
- Cross-validation is used to reduce overfitting

---

## 🏆 Best Model Selection
Based on validation accuracy and consistency, the best-performing model is selected and trained on the full training dataset before generating test predictions.

---

## 📤 Kaggle Submission
Predictions are generated for the test dataset and saved in the Kaggle-required format:

```csv
id,booking_status
1,0
2,1


Results & Performance

Accuracy Score Achieved: 0.8928

Highest Leaderboard Score: 0.9031

Leaderboard Rank: 131

Total Participants: 1000+