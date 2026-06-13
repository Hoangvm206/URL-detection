# AI Cyber Shield - Phishing URL Detection

AI Cyber Shield is a machine learning-based phishing URL detection system designed to identify malicious URLs through security feature engineering and behavioral analysis. The project combines cybersecurity knowledge with machine learning techniques to provide real-time phishing detection.

---

## Features

* Phishing URL detection using Machine Learning
* Security-focused feature engineering
* URL structure analysis
* Domain reputation analysis
* DNS and HTTPS validation
* Typosquatting detection
* Sensitive keyword detection
* Website behavior analysis
* Risk score assessment

---

## Architecture

```text
URL Input
    │
    ▼
Feature Extraction
(URL + Domain + HTML Features)
    │
    ▼
Data Preprocessing
(SMOTE Balancing)
    │
    ▼
Machine Learning Models
├── Naive Bayes
└── Random Forest
    │
    ▼
Risk Assessment
    │
    ▼
Detection Result
(SAFE / MEDIUM RISK / HIGH RISK)
```

---

## Dataset

The training dataset was built from multiple phishing URL sources and processed into a balanced training set.

### Dataset Statistics

* Total URLs: 41,536
* Binary Classification:

  * Legitimate URLs
  * Phishing URLs
* Data balancing using SMOTE

---

## Security Features

The system extracts security-relevant indicators from each URL.

### URL Features

* URL Length
* URL Entropy
* Number of Subdomains
* IP Address Usage
* URL Shortening Services
* Sensitive Keyword Count

### Domain Features

* HTTPS Status
* Domain Age
* DNS Records
* Google Index Status
* Web Traffic Reputation
* Typosquatting Score

### Website Behavior Features

* External Links
* Form Handling
* Redirect Analysis
* Iframe Detection
* JavaScript Behavior
* Popup Detection

---

## Machine Learning Models

### Naive Bayes

A lightweight probabilistic classifier used as a baseline model.

### Random Forest

An ensemble learning model consisting of 100 decision trees used for final phishing classification.

---

## Results

| Model         | Accuracy | Precision | Recall | F1-Score |
| ------------- | -------- | --------- | ------ | -------- |
| Naive Bayes   | 84.76%   | 93.32%    | 87.24% | 90.17%   |
| Random Forest | 93.27%   | 97.55%    | 93.96% | 95.72%   |

Random Forest achieved the best overall performance and was selected as the primary detection model.

---

## Project Structure

```text
AI-Cyber-Shield/
│
├── src/
│   ├── feature_extractor.py
│   ├── train.py
│   └── malicious_url_detector.py
│
├── models/
│   ├── naive_bayes_model.pkl
│   └── random_forest_model.pkl
│
├── screenshots/
│
├── requirements.txt
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone https://github.com/Hoangvm206/URL-detection.git
cd URL-detection
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Model Training

Train the machine learning models:

```bash
python train.py
```

Generated models:

```text
naive_bayes_model.pkl
random_forest_model.pkl
```

---

## URL Analysis

Analyze a URL using the trained model:

```bash
python malicious_url_detector.py
```

Example:

```text
Enter a URL:
https://example-login-security.com
```

Output:

```text
Risk Score: 92.3%
Classification: Phishing
```

---

## Technologies Used

* Python
* Scikit-learn
* Pandas
* NumPy
* BeautifulSoup
* Requests
* WHOIS
* SMOTE
* Random Forest
* Naive Bayes

---

## Author

**Vu Minh Hoang(Team Leader)**
**Vu Minh Tu**
**Vu Tien Thanh**
**Ngo Duc Thang**
