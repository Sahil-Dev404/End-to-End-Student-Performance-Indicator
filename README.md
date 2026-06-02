# 🎓 Student Performance Predictor

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.0+-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![CatBoost](https://img.shields.io/badge/CatBoost-Latest-FFCC00?style=for-the-badge)](https://catboost.ai)
[![Render](https://img.shields.io/badge/Deployed%20on-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://render.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

An end-to-end machine learning web application that predicts a student's **math score** based on demographic and academic background features. Built with a modular ML pipeline architecture and deployed on Render.

🔗 **Live Demo:** [https://end-to-end-student-performance-indicator.onrender.com](https://end-to-end-student-performance-indicator.onrender.com)  
📁 **GitHub:** [https://github.com/Sahil-Dev404/End-to-End-Student-Performance-Indicator](https://github.com/Sahil-Dev404/End-to-End-Student-Performance-Indicator)

---

## 📸 Screenshots

### Home Page
![Home Page](/screenshots/index.png)

### Prediction Result
![Prediction Result 1](screenshots/home1.png)
![Prediction Result 2](screenshots/home2.png)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [ML Pipeline](#-ml-pipeline)
- [Model Performance](#-model-performance)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Contributing](#-contributing)

---

## 🔍 Overview

This project predicts a student's **math score** using 7 input features including gender, race/ethnicity, parental education level, lunch type, test preparation course, reading score, and writing score.

The dataset contains **1,000 student records** and the project benchmarks **9 regression models** to select the best-performing one. The final model is served via a **Flask web application** deployed on Render for real-time inference.

---

## ✨ Features

- 📊 **End-to-end ML pipeline** — from raw data to deployed prediction API
- 🔁 **Modular architecture** — separate components for ingestion, transformation, and training
- 🤖 **9 models benchmarked** — Linear Regression, Ridge, Lasso, KNN, Decision Tree, Random Forest, XGBoost, CatBoost, AdaBoost
- 🏆 **R² score of 0.88** achieved with Linear Regression as the final model
- 🌐 **Flask web app** with a clean form-based UI for real-time score prediction
- 📋 **Logging & exception handling** throughout the pipeline
- ☁️ **Deployed on Render** with Git-based continuous deployment

---

## 🛠 Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.8+ |
| ML Libraries | Scikit-learn, CatBoost, XGBoost |
| Data Processing | Pandas, NumPy |
| Web Framework | Flask |
| Frontend | HTML, CSS (Jinja2 templates) |
| Deployment | Render |
| Version Control | Git, GitHub |
| Development | Jupyter Notebook, VS Code |

---

## 📁 Project Structure

```
Student-Performance-Predictor/
│
├── artifacts/                  # Saved model and data artifacts
│   ├── data.csv                # Raw dataset
│   ├── model.pkl               # Trained model
│   ├── preprocessor.pkl        # Fitted preprocessor
│   ├── train.csv               # Training split
│   └── test.csv                # Test split
│
├── catboost_info/              # CatBoost training logs
│
├── logs/                       # Application logs
│
├── Notebook/                   # EDA and model training notebooks
│   ├── data/
│   ├── EDA student perform...  # Exploratory Data Analysis
│   └── Model Training.ipynb    # Model benchmarking and selection
│
├── src/                        # Core source code
│   ├── components/             # ML pipeline components
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/               # Prediction pipeline
│   │   └── predict_pipeline.py
│   ├── __init__.py
│   ├── exception.py            # Custom exception handling
│   ├── logger.py               # Logging configuration
│   └── utils.py                # Utility functions
│
├── templates/                  # Flask HTML templates
│   ├── home.html               # Landing page
│   └── index.html              # Prediction form
│
├── app.py                      # Flask application entry point
├── .gitignore
└── requirements.txt
```

---

## 🔄 ML Pipeline

```
Raw Data (1,000 records, 8 columns)
        │
        ▼
Data Ingestion
(train/test split → saved to artifacts/)
        │
        ▼
Data Transformation
(OneHotEncoding for categoricals + StandardScaler for numericals)
        │
        ▼
Model Training
(9 models benchmarked with cross-validation)
        │
        ▼
Best Model Selection
(Linear Regression → R² = 0.88)
        │
        ▼
Model Serialization
(model.pkl + preprocessor.pkl → artifacts/)
        │
        ▼
Flask Web App → Render Deployment
```

---

## 📈 Model Performance

| Model | R² Score |
|---|---|
| **Linear Regression** ✅ | **0.88** |
| Ridge Regression | 0.88 |
| Random Forest | 0.85 |
| XGBoost | 0.83 |
| CatBoost | 0.82 |
| AdaBoost | 0.81 |
| Lasso | 0.79 |
| Decision Tree | 0.76 |
| KNN | 0.74 |

> ✅ Linear Regression selected as final model for its best generalization with minimal complexity.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Git

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/Sahil-Dev404/End-to-End-Student-Performance-Indicator.git
cd End-to-End-Student-Performance-Indicator
```

2. **Create a virtual environment**
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the training pipeline**
```bash
python src/components/data_ingestion.py
```

5. **Start the Flask app**
```bash
python app.py
```

6. **Open in browser**
```
http://localhost:5000
```

---

## 💻 Usage

1. Navigate to the web app (local or live demo)
2. Fill in the student details:
   - Gender
   - Race / Ethnicity
   - Parental Level of Education
   - Lunch Type
   - Test Preparation Course
   - Reading Score
   - Writing Score
3. Click **Predict**
4. View the predicted **Math Score** instantly

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 👨‍💻 Author

**Sahil Saini**  
B.Tech AI & ML — GGSIPU '28  
📧 [2005sahilsaini@gmail.com](mailto:2005sahilsaini@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/sahil-saini-a47b40324)  
💻 [GitHub](https://github.com/Sahil-Dev404)

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

⭐ **If you found this project helpful, please give it a star!**