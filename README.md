## Simple Linear Regression Using Machine Learning

### 📌 Project Overview

This project demonstrates the implementation of **Simple Linear Regression** using **Machine Learning** to predict **Salary** based on **Years of Experience**.

The dataset used in this project is **salary.csv**, which contains **30 rows** and **2 columns**:

* **YearsExperience** → Input feature (X)
* **Salary** → Target variable (Y)

The model was trained, tested, integrated with a **Flask web application**, and finally **deployed on Render Cloud**, allowing anyone to access the application through a public URL.

---

## 🚀 Features

* Data collection and preprocessing
* Train-test split (80:20)
* Simple Linear Regression using **y = mx + c**
* Model serialization using **pickle**
* Flask-based web interface
* Deployment on **Render**
* Publicly accessible prediction system

---

## 📂 Dataset Information

**File:** `salary.csv`

| Column          | Description                            |
| --------------- | -------------------------------------- |
| YearsExperience | Number of years of work experience     |
| Salary          | Salary corresponding to the experience |

### Total Records

* **30 rows**
* **2 columns**

---

## 🔍 Train-Test Split

The dataset was divided using an **80:20 ratio**.

| Type          | Records |
| ------------- | ------- |
| Training Data | 24      |
| Testing Data  | 6       |

The split was performed **randomly** to avoid bias and improve generalization.

---

## 🤖 Model Used

### Simple Linear Regression

The mathematical equation used:

```python
y = mx + c
```

Where:

* **y** = Predicted Salary
* **m** = Slope
* **x** = Years of Experience
* **c** = Intercept

The **24 training samples** were used to train the linear regression model.

---

## 📈 Model Performance

### Training Results

* **Training Accuracy:** ~96%
* **Training Loss:** ~5000

The **actual salary points** and **predicted salary points** were **very close**, indicating that the model learned the relationship effectively.

### Testing Results

* **Testing Accuracy:** ~90%
* **Testing Loss:** ~2000

The model also performed well on unseen data, showing good **generalization capability**.

---

## ❓ Why Gradient Descent Was Not Used

This project uses **Scikit-learn's LinearRegression()** implementation.

Scikit-learn calculates the **optimal slope and intercept directly using the Ordinary Least Squares (OLS) method**, so **manual Gradient Descent is not required**.

### Benefits of this approach

* Faster computation
* Simpler implementation
* Accurate closed-form solution
* Suitable for small datasets like this one

---

## 💾 Model Serialization

After training, the model was saved using **pickle**.

### Example

```python
import pickle

pickle.dump(model, open('model.pkl', 'wb'))
```

### Purpose of Pickle

* Saves the trained model to a file
* Avoids retraining every time
* Enables reuse in Flask applications and deployment

---

## 🐍 Virtual Environment Explanation

A **virtual environment** was created in **PyCharm**.

### Why is a Virtual Environment Needed?

A virtual environment creates an **isolated Python environment** for the project.

### Advantages

* Keeps project dependencies separate
* Prevents version conflicts
* Makes deployment easier
* Ensures the project runs consistently on other systems

### Example

```bash
python -m venv venv
```

### Activation

#### Windows

```bash
venv\Scripts\activate
```

Once activated, packages such as **Flask**, **scikit-learn**, **numpy**, and **gunicorn** are installed only inside this environment.

---

## 🌐 Flask Web Application

The project was converted into a **web application** using **Flask**.

### Project Structure

```text
simple-linear-regression/
│
├── app.py
├── model.pkl
├── salary.csv
├── requirments.txt
├── Procfile
│
├── templates/
│   └── index.html
│
└── README.md
```

---

## 🖥️ Frontend

The frontend was developed using **HTML** inside the **templates** folder.

### File

```text
templates/index.html
```

The user enters **Years of Experience**, and the application displays the **predicted salary**.

---

## ⚙️ Backend

### File

```python
app.py
```

Responsibilities:

* Load the pickle model
* Receive user input from the form
* Convert input into numeric format
* Predict salary using the trained model
* Return the result to the webpage

---

## ▶️ Running Locally

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run Flask

```bash
python app.py
```

### Local URL

```text
http://127.0.0.1:5000/
```

The outputs were successfully tested on the **local server**.

---

## ☁️ Deployment on Render

To make the project accessible online, it was deployed using **Render Cloud Platform**.

### Additional Files Used

#### Procfile

```text
web: gunicorn app:app
```

#### Gunicorn Installation

```bash
pip install gunicorn
```

### Deployment Steps

1. Push project to GitHub
2. Connect GitHub repository to Render
3. Set build command:

```bash
pip install -r requirments.txt
```

4. Set start command:

```bash
gunicorn app:app
```

After deployment, Render generates a **public URL**, and **anyone can access the application by clicking the link**.

---

## 🔗 Project Links

### GitHub Repository

👉 **Add your GitHub repository link here**

```text
https://github.com/sribhavyamandapati/SlR_Model/
```

### Live Demo / Render Link

👉 **Add your Render deployment link here**

```text
https://slr-model-2-mt16.onrender.com
```

### Trained Model Download Link


---

## 🛠️ Technologies Used

| Technology   | Purpose                 |
| ------------ | ----------------------- |
| Python       | Programming Language    |
| Pandas       | Data Handling           |
| NumPy        | Numerical Operations    |
| Scikit-learn | Machine Learning        |
| Flask        | Web Framework           |
| HTML         | Frontend                |
| Pickle       | Model Serialization     |
| Gunicorn     | Production Server       |
| Render       | Cloud Deployment        |
| PyCharm      | Development Environment |

---

## 📊 Sample Prediction Flow

```text
Input:
Years of Experience = 5

Model Prediction:
Predicted Salary = ₹72440.6596269317
```

The prediction is generated using the **trained linear regression model** loaded from `model.pkl`.

---

## 🎯 Conclusion

This project successfully demonstrates a **complete Machine Learning workflow**:

### ✔️ Data Collection

Collected salary data with **Years of Experience** and **Salary** columns.

### ✔️ Data Splitting

Used **80% training data** and **20% testing data**.

### ✔️ Model Training

Trained a **Simple Linear Regression** model using the equation:

```text
y = mx + c
```

### ✔️ Model Evaluation

* **Training Accuracy:** ~96%
* **Testing Accuracy:** ~90%

The predicted values were **very close to the actual values**, indicating good model performance.

### ✔️ Model Saving

Saved the trained model using **pickle** for reuse.

### ✔️ Web Integration

Integrated the model with a **Flask web application** using:

* `index.html` for the frontend
* `app.py` for the backend

### ✔️ Deployment

Deployed the application on **Render Cloud** using **Gunicorn** and **Procfile**, making it **publicly accessible through a generated URL**.

This project provides a **simple, efficient, and fully deployable salary prediction system** and serves as an excellent beginner-level **Machine Learning + Flask + Deployment project**.

---
