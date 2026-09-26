ML_HEART_project

❤️ Heart Disease Prediction Machine Learning Project

🚀 Project Overview

This project is a Machine Learning classification application that analyzes heart-disease data and predicts the target outcome using multiple classification algorithms.

The project covers the complete Machine Learning workflow:

Data Loading

Data Validation

Train-Test Split

Yeo-Johnson Transformation

Constant Feature Removal

Quasi-Constant Feature Removal

Hypothesis Testing / Feature Selection

Training Data Balancing

Model Training

Model Evaluation

Confusion Matrix

Classification Report

ROC Curve Visualization

Prediction through a Web Interface

Logging of Pipeline Execution

The project is developed using Python, Pandas, NumPy, Scikit-Learn, XGBoost, Matplotlib, Seaborn, and Flask/HTML.

📌 Problem Statement

Heart-disease datasets contain multiple patient-related attributes that can be used to build a classification model.

The objective of this project is to process the available features, select relevant features, train multiple classification algorithms, and predict the target class for new input data.

Input

The final model uses the following seven processed features:

age_yeo_trim
sex_yeo_trim
cp_yeo_trim
thalach_yeo_trim
oldpeak_yeo_trim
slope_yeo_trim
thal_yeo_trim

Output

The trained classification model produces a predicted target class.

📊 Dataset Information

The current dataset contains:

Information

Value

Total Records

303

Total Columns

14

Input Features

13

Target Column

target

Missing Values

0

Training Records

242

Testing Records

61

The original input features include:

age
sex
cp
trestbps
chol
fbs
restecg
thalach
exang
oldpeak
slope
ca
thal

🔄 Machine Learning Pipeline

The complete pipeline is:

Dataset
   ↓
Data Validation
   ↓
Train / Test Split
   ↓
Yeo-Johnson Transformation
   ↓
Constant Feature Removal
   ↓
Quasi-Constant Feature Removal
   ↓
Hypothesis Testing
   ↓
Feature Selection
   ↓
Training Data Balancing
   ↓
Model Training
   ↓
Model Evaluation
   ↓
ROC Curve
   ↓
Prediction

🧹 Data Preprocessing

1. Train-Test Split

The dataset is divided into:

Training Data : 242 records
Testing Data  : 61 records

2. Yeo-Johnson Transformation

The project applies a Yeo-Johnson transformation to the input features.

The transformed features are represented with the _yeo_trim suffix.

Example:

age      → age_yeo_trim
sex      → sex_yeo_trim
cp       → cp_yeo_trim

🔍 Feature Selection

The project performs multiple feature-selection steps.

1. Constant Feature Removal

The following feature was removed:

fbs_yeo_trim

Remaining features:

12

2. Quasi-Constant Feature Removal

The following features were removed:

trestbps_yeo_trim
chol_yeo_trim
exang_yeo_trim
ca_yeo_trim

Remaining features:

8

3. Hypothesis Testing

P-values are calculated for the selected features.

The following feature was removed based on the logged hypothesis-testing result:

restecg_yeo_trim

Final Features

The final model uses:

age_yeo_trim
sex_yeo_trim
cp_yeo_trim
thalach_yeo_trim
oldpeak_yeo_trim
slope_yeo_trim
thal_yeo_trim

Final number of features:

7

⚖️ Training Data Balancing

Before balancing:

Class 1 : 133
Class 0 : 109
Total   : 242

After balancing:

Class 1 : 133
Class 0 : 133
Total   : 266

The test data remains separate from the training-data balancing process.

🤖 Machine Learning Algorithms

The project evaluates eight classification algorithms:

K-Nearest Neighbors

Gaussian Naive Bayes

Logistic Regression

Decision Tree

Random Forest

AdaBoost

Gradient Boosting

XGBoost

📈 Model Performance

The current test run produced the following accuracy values:

Model

Test Accuracy

K-Nearest Neighbors

57.38%

Gaussian Naive Bayes

80.33%

Logistic Regression

59.02%

Decision Tree

60.66%

Random Forest

50.82%

AdaBoost

59.02%

Gradient Boosting

62.30%

XGBoost

55.74%

These values represent the current test-set results from this project run.

📋 Model Evaluation

Each model generates:

Accuracy

Confusion Matrix

Classification Report

The classification report contains:

Precision

Recall

F1-score

Support

🧮 Example: Naive Bayes Evaluation

The current Naive Bayes run produced:

Test Accuracy : 0.8032786885245902

Confusion Matrix

[[25  4]
 [ 8 24]]

Classification Report

              precision    recall  f1-score   support

0                0.76       0.86      0.81        29
1                0.86       0.75      0.80        32

accuracy                              0.80        61
macro avg          0.81       0.81      0.80        61
weighted avg       0.81       0.80      0.80        61

📉 ROC Curve

The project generates an ROC curve visualization for:

KNN
LR
NB
DT
RF
ADA
GB
XGB

The current implementation generates the ROC curves using the model predictions.

For a production-level ROC-AUC evaluation, probability or decision scores should be used when supported by the model.

📝 Logging

The project maintains separate log files for different stages.

logs/
│
├── main.log
├── fs.log
├── yeo_timing.log
└── all_models.log

main.log

Stores:

Dataset shape

Null-value information

Train/test data size

Class distribution

Balancing information

Main model output

fs.log

Stores:

Feature-selection information

Constant-feature removal

Quasi-constant-feature removal

P-values

Hypothesis-testing results

yeo_timing.log

Stores:

Feature names before transformation

Feature names after transformation

all_models.log

Stores:

KNN results

Naive Bayes results

Logistic Regression results

Decision Tree results

Random Forest results

AdaBoost results

Gradient Boosting results

XGBoost results

ROC execution information

🌐 Web Application

The project includes an HTML-based prediction interface.

The user enters the seven final processed features:

Age
Sex
Chest Pain Type
Maximum Heart Rate
ST Depression
Slope
Thal

The form sends the values to the backend, which can then pass them to the trained model and return the prediction.

📂 Project Structure

ML_HEART_project/
│
├── main.py
├── all_models.py
├── fs.py
├── yeo_timing.py
├── log_code.py
├── index.html
├── requirements.txt
│
├── logs/
│   ├── main.log
│   ├── fs.log
│   ├── yeo_timing.log
│   └── all_models.log
│
└── README.md

If Flask is used with Jinja templates, the HTML file can be placed under:

templates/
└── index.html

⚙️ Installation

Step 1: Clone the Repository

git clone <your-github-repository-url>

Step 2: Open the Project

cd ML_HEART_project

Step 3: Create Virtual Environment

python -m venv venv

Step 4: Activate Virtual Environment

Windows

venv\Scripts\activate

Step 5: Install Dependencies

pip install -r requirements.txt

▶️ Run the Machine Learning Pipeline

From the project directory:

python main.py

The pipeline processes the dataset, performs feature selection, balances the training data, trains the models, evaluates them, and writes execution information to the logs directory.

🖥️ Run the Web Application

If the project uses Flask, start the Flask application using the command defined in your backend.

Example:

python app.py

Then open the local application URL shown by Flask in the browser.

🛠️ Technologies Used

Python

Pandas

NumPy

Scikit-Learn

XGBoost

Matplotlib

Seaborn

Flask

HTML

CSS

Git

GitHub

🎯 Future Enhancements

Improve model hyperparameter tuning

Add cross-validation

Add proper ROC-AUC calculation using probability/decision scores

Add model comparison visualization

Save trained models using Pickle or Joblib

Add prediction API

Add database integration

Improve frontend validation

Add Docker support

Add CI/CD pipeline

Deploy the application to a cloud platform

👨‍💻 Author

Sai Chandrika Vanka

Java Full Stack Developer | Machine Learning Enthusiast

📧 Email: vankasaichandrika@gmail.com

⚠️ Disclaimer

This project is intended for machine-learning development and educational purposes.

The predictions generated by this application should not be treated as a medical diagnosis or as a substitute for professional medical advice.
