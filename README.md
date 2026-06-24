# SimpleLinearRegression
# 📈 Simple Linear Regression Salary Prediction Project

## 🚀 Project Overview

This project demonstrates the implementation of a **Simple Linear Regression Machine Learning Model** using **Python**, **Scikit-Learn**, and **Flask**.

The objective of this project is to predict the **Salary** of a person based on their **Years of Experience**.

The project covers the complete Machine Learning lifecycle:

* Data Collection
* Data Preprocessing
* Model Training
* Model Evaluation
* Prediction on New Data
* Model Serialization using Pickle
* Flask Web Application Development
* HTML Frontend Development
* Deployment Preparation for Render Cloud

---

# 📌 Problem Statement

Organizations often want to estimate an employee's salary based on their years of experience.

In this project, we use **Simple Linear Regression** to learn the relationship between:

### Independent Variable (X)

Experience (Years)

### Dependent Variable (Y)

Salary

After training the model, users can enter experience through a web page and receive the predicted salary instantly.

---

# 📊 Dataset Information

The dataset contains:

| Feature    | Description                   |
| ---------- | ----------------------------- |
| Experience | Number of years of experience |
| Salary     | Corresponding salary          |

### Dataset Size

* Total Records: 30
* Training Data: 24 Records (80%)
* Testing Data: 6 Records (20%)

---

# 🤖 Machine Learning Algorithm Used

## Simple Linear Regression

Simple Linear Regression is a supervised machine learning algorithm used to find the relationship between:

* One Independent Variable (X)
* One Dependent Variable (Y)

It fits the best straight line through the data points.

---

# 📐 Mathematical Formula

The Simple Linear Regression equation is:

```text
Y = mX + b
```

Where:

* Y = Predicted Value
* X = Input Feature (Experience)
* m = Slope of the Line
* b = Intercept

### Example

```text
Salary = m × Experience + b
```

The algorithm learns the values of m and b during training.

---

# 📈 Model Training Process

### Step 1: Import Required Libraries

```python
import pandas as pd
import numpy as np
from sklearn.linear_model import LinearRegression
```

### Step 2: Load Dataset

```python
df = pd.read_csv("salary_data.csv")
```

### Step 3: Split Dataset

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Training Records = 24

Testing Records = 6

---

### Step 4: Train Model

```python
model = LinearRegression()

model.fit(X_train, y_train)
```

The model learns:

* Slope (m)
* Intercept (b)

---

# 📊 Model Performance

## Training Accuracy (R² Score)

```text
96%
```

## Testing Accuracy (R² Score)

```text
90%
```

The model performs well on both training and testing datasets, indicating good generalization.

---

# 📚 Evaluation Metrics

## 1. R² Score (Coefficient of Determination)

R² Score measures how well the regression line fits the data.

### Formula

```text
R² = 1 - (SSres / SStot)
```

Where:

```text
SSres = Σ(yactual - ypredicted)²

SStot = Σ(yactual - ymean)²
```

### Interpretation

| R² Score | Meaning            |
| -------- | ------------------ |
| 1.0      | Perfect Prediction |
| 0.9+     | Excellent Model    |
| 0.8+     | Good Model         |
| 0.5      | Moderate           |
| 0        | Poor Model         |

### Project Result

```text
Training R² = 96%

Testing R² = 90%
```

---

## 2. Mean Squared Error (MSE)

MSE measures the average squared difference between actual and predicted values.

### Formula

```text
MSE = (1/n) Σ(yactual - ypredicted)²
```

### Project Result

```text
Train Loss (MSE) = 150

Test Loss (MSE) = 189
```

Lower MSE indicates better performance.

---

## 3. Root Mean Squared Error (RMSE)

RMSE is the square root of MSE.

### Formula

```text
RMSE = √MSE
```

### Advantages

* Easy to interpret
* Same unit as target variable
* Commonly used in regression problems

Lower RMSE indicates better prediction accuracy.

---

# 🔮 Prediction on New Data

After training the model, predictions can be made on unseen data.

Example:

```python
experience = [[5]]

salary = model.predict(experience)

print(salary)
```

Output:

```text
Predicted Salary
```

The model uses the learned regression equation to estimate the salary.

---

# 💾 Model Serialization Using Pickle

After successful training, the model is saved into a Pickle file.

### Saving Model

```python
import pickle

pickle.dump(model, open("SLR_MODEL.pkl", "wb"))
```

### Loading Model

```python
model = pickle.load(open("model.pkl", "rb"))
```

---

# Why Use Pickle?

### Advantages

✅ Stores trained model permanently

✅ No need to retrain every time

✅ Faster application startup

✅ Easy deployment

✅ Saves computation time

---

# 🌐 Flask Web Application

Flask is a lightweight Python web framework used to build web applications.

In this project Flask acts as a bridge between:

```text
Frontend (HTML)
        ↓
Flask Backend
        ↓
Machine Learning Model
        ↓
Prediction Result
```

---

# 📂 Project Structure

```text
Salary-Prediction-Project
│
├── SLR_MODEL.pkl
├── app.py
├── requirements.txt
├── Procfile
│
├── templates
│   └── index.html
│
├── static
│   └── style.css
│
└── README.md
```

---

# ⚙️ app.py Explanation

The app.py file is the backend of the application.

### Responsibilities

✔ Load Trained Model

✔ Receive User Input

✔ Convert Input into Required Format

✔ Predict Salary

✔ Send Prediction to Frontend

---

### Basic Workflow

```text
User enters Experience
          ↓
HTML Form Submit
          ↓
Flask Receives Data
          ↓
Model Predicts Salary
          ↓
Result Displayed
```

---

# 📝 HTML Frontend Explanation

The HTML page provides the user interface.

### Responsibilities

✔ Accept Experience Input

✔ Send Data to Flask

✔ Display Predicted Salary

---

### Example Components

```html
<input type="text">

<button>
Predict
</button>
```

---

### User Flow

```text
Open Website
      ↓
Enter Experience
      ↓
Click Predict
      ↓
Prediction Generated
      ↓
Result Displayed
```

---

# 📦 Virtual Environment

A Virtual Environment is an isolated Python environment.

### Creation

```bash
python -m venv venv
```

### Activate

Windows:

```bash
venv\Scripts\activate
```

---

# Why Use Virtual Environment?

### Advantages

✅ Dependency Isolation

✅ Version Management

✅ Project Independence

✅ Easy Deployment

✅ Cleaner Development Environment

---

# 📋 requirements.txt

This file contains all required Python packages.

Example:

```text
Flask
numpy
pandas
scikit-learn
pickle-mixin
gunicorn
```

---

# Advantages of requirements.txt

### 1. Easy Installation

```bash
pip install -r requirements.txt
```

### 2. Reproducibility

Every developer gets the same environment.

### 3. Deployment Friendly

Cloud platforms install packages automatically.

### 4. Version Control

Ensures consistent library versions.

---

# 🚀 Procfile Explanation

A Procfile tells cloud platforms how to run the application.

Example:

```text
web: gunicorn app:app
```

---

# Why Procfile is Important?

### Advantages

✅ Required for deployment

✅ Defines startup command

✅ Helps Render execute Flask application

✅ Simplifies cloud deployment

---

# ☁️ Deployment on Render

This project is prepared for deployment on Render Cloud.

### Deployment Steps

1. Push code to GitHub
2. Create Render account
3. Connect GitHub repository
4. Select Web Service
5. Add requirements.txt
6. Add Procfile
7. Deploy Application

Render automatically:

* Installs dependencies
* Creates build
* Starts Flask server
* Hosts application online

---

# 🛠️ Technologies Used

* Python
* Machine Learning
* Scikit-Learn
* Pandas
* NumPy
* Flask
* HTML
* CSS
* Pickle
* Git
* GitHub
* Render Cloud

---

# 🎯 Future Enhancements

* Responsive UI Design
* Database Integration
* User Authentication
* Multiple Feature Prediction
* Docker Containerization
* CI/CD Pipeline
* AWS Deployment
* REST API Integration

---

# 👨‍💻 Author

### Sai Chandrika Vanka

Java Full Stack Developer | Machine Learning Enthusiast

📧 Email:

[vankasaichandrika@gmail.com](mailto:vankasaichandrika@gmail.com)

### LinkedIn

(Add your LinkedIn profile URL here)

Example:

https://www.linkedin.com/in/your-profile/

---

# 🤝 Connect With Me

If you have any suggestions, improvements, or collaboration opportunities, feel free to connect with me.

📧 Email: [vankasaichandrika@gmail.com](mailto:vankasaichandrika@gmail.com)

---

# ⭐ Support

If you found this project helpful:

⭐ Star the Repository

🍴 Fork the Repository

📢 Share with Others

Happy Learning and Happy Coding!
