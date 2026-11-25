# 📡 End-to-End Machine Learning & AI Retention Pipeline

An end-to-end Data Science and Machine Learning project covering **web data collection**, **multi-dataset model benchmarking**, **interactive Streamlit deployment with Gemini AI**, and **automated daily batch scoring**.

---

## 🏗️ Project Architecture

```text
├── day5_ex0_scraping_bridge.py      # Web scraping & feature engineering (BeautifulSoup + Google Play)
├── day5_ex1_train_and_save.py       # Model benchmarking (Logistic Regression vs. Random Forest) & serialization
├── day5_ex2_trainer_app.py          # Interactive Streamlit web dashboard with Gemini 2.5 Flash advisor
├── day5_ex3_daily_batch_predict.py  # Automated daily batch scoring pipeline for medical no-shows
├── customer_churn.csv               # Telecom customer churn dataset (200 records)
├── project_ecommerce_orders.csv     # E-commerce order returns dataset (200 records)
├── project_hr_attrition.csv         # HR employee attrition dataset (200 records)
├── project_medical_appointments.csv # Medical clinic no-show dataset (200 records)
├── models/                          # Serialized winning models, column schemas, and feature importances (.pkl)
└── requirements.txt                 # Python dependencies
