 Phishing URL Detection

A Machine Learning-based web application that detects whether a given URL is **Phishing** or **Legitimate** using a Random Forest classifier.

Project Overview

Phishing websites are designed to trick users into sharing sensitive information such as usernames, passwords, and other personal details. This project analyzes URL-level characteristics and uses Machine Learning to identify potentially suspicious URLs.

The system takes a URL from the user, extracts important URL features, sends them to a trained Random Forest model, and displays the predicted result through a Streamlit dashboard.

How the Project Works

text
User enters URL
       ↓
URL Feature Extraction
       ↓
9 URL-level Features
       ↓
Random Forest ML Model
       ↓
Prediction
       ↓
PHISHING / LEGITIMATE
       ↓
Streamlit Dashboard


URL Features Used

The URL-only model uses the following 9 features:

- IP Address detection
- URL Length
- URL Shortening Service
- `@` Symbol
- Double Slash Redirecting
- Prefix/Suffix
- Subdomain
- Port
- HTTPS Token

These features are converted into numerical values and provided to the Machine Learning model.

Machine Learning Model

We used a **Random Forest Classifier** for phishing URL classification.

The model was trained using the prepared phishing URL dataset and saved as:

text
models/url_only_model.joblib


The dataset contains **11,055 records** with phishing and legitimate URL-related feature data.

Model Performance

The URL-only Random Forest model was evaluated using a held-out test dataset.

Metric           Score 

Accuracy        74.17% 
Precision       83.67% 
Recall          66.61%
F1 Score        74.17% 

These values represent the overall performance of the trained model on the test dataset and are not the accuracy of an individual URL.

 Web Application

The project uses Streamlit to provide a simple web interface.

The user can:

1. Enter a URL.
2. Click the analysis button.
3. Extract URL-level features.
4. Get a Machine Learning prediction.
5. View the result as **Phishing** or **Legitimate**.
6. View the model performance metrics.

Project Structure

text
Phishing-URL-Detection/
│
├── dataset/
│   ├── PhishingData.csv
│   └── phishingdata_clean.csv
│
├── models/
│   ├── random_forest_model.joblib
│   └── url_only_model.joblib
│
├── src/
│   ├── app.py
│   ├── url_analyzer.py
│   ├── train_model.py
│   ├── train_url_model.py
│   └── prepare_dataset.py
│
├── README.md
└── requirements.txt

Technologies Used

Python
Pandas
Scikit-learn
Random Forest
Joblib
Streamlit

 How to Run
 
 1. Create and activate the virtual environment

python -m venv .venv


Windows:

powershell

.\.venv\Scripts\Activate.ps1

2. Install dependencies

powershell

pip install -r requirements.txt

 3. Train the URL-only model

powershell
.\.venv\Scripts\python.exe src\train_url_model.py

 4. Run the Streamlit application

powershell
.\.venv\Scripts\python.exe -m streamlit run src/app.py


The application will open in the browser.

Testing

The application can be tested using different
