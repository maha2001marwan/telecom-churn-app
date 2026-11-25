
```markdown
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

```

---

## 🚀 Key Modules

### 1. Data Collection & Feature Engineering (`day5_ex0_scraping_bridge.py`)

* Scrapes product listings (titles, prices, star ratings, stock status) from HTML pages using `requests` and `BeautifulSoup`.
* Fetches live app reviews from Google Play Store using `google-play-scraper` and derives sentiment labels and numerical text features.

### 2. Model Benchmarking & Serialization (`day5_ex1_train_and_save.py`)

* Evaluates **Logistic Regression** vs. **Random Forest** across four business datasets (`Telecom Churn`, `E-Commerce Returns`, `HR Attrition`, and `Medical No-Show`) using a stratified 70/30 train-test split.
* Exports the top-performing model (`_model.pkl`), exact encoded column alignment (`_columns.pkl`), and feature importance scores (`_importance.pkl`) into `models/`.

| Dataset | Winning Model | Test Accuracy | Test Recall |
| --- | --- | --- | --- |
| **Telecom Customer Churn** | Logistic Regression | 86.67% | 66.67% |
| **E-Commerce Order Returns** | Logistic Regression | 71.67% | 76.47% |
| **HR Employee Attrition** | Logistic Regression | 90.00% | 57.14% |
| **Medical Clinic No-Show** | Random Forest | 75.00% | 77.42% |

### 3. Live Web Application (`day5_ex2_trainer_app.py`)

* **Executive KPIs & Segment Filtering:** Filter customer segments by city and contract type using cached data loading (`@st.cache_data`).
* **Real-Time Churn Risk Prediction:** Predicts individual customer churn probability on the fly using cached model artifacts (`@st.cache_resource`).
* **AI Retention Strategist:** Integrates **Gemini 2.5 Flash** (`google-genai`) to generate tailored 3-step retention plans, with a built-in rule-based fallback for offline resilience.

### 4. Automated Batch Scoring (`day5_ex3_daily_batch_predict.py`)

* Designed for scheduled execution (`Cron` / `GitHub Actions`).
* Scores upcoming clinic appointments using `models/med_model.pkl`, flags high-risk records (`probability >= 0.45`), and exports a prioritized call list to `daily_high_risk_appointments.csv`.

---

## 🛠️ Local Setup & Usage

1. **Clone the repository:**
```bash
git clone <YOUR_REPO_URL>
cd <YOUR_REPO_NAME>

```


2. **Install dependencies:**
```bash
pip install -r requirements.txt

```


3. **Train and serialize the models:**
```bash
python day5_ex1_train_and_save.py

```


4. **Launch the Streamlit web application:**
```bash
streamlit run day5_ex2_trainer_app.py

```


5. *(Optional)* **Enable Gemini AI Retention Advice:**
Set your API key as an environment variable (or in `.streamlit/secrets.toml` when deploying to Streamlit Cloud):
```bash
export GEMINI_API_KEY="your_api_key_here"

```


6. *(Optional)* **Run the daily batch scoring script:**
```bash
python day5_ex3_daily_batch_predict.py

```



---

## 🧰 Tech Stack

* **Language:** Python 3
* **Data & ML:** Pandas, NumPy, Scikit-Learn, Joblib
* **Web & GenAI:** Streamlit, Google GenAI SDK (`gemini-2.5-flash`)
* **Web Scraping:** Requests, BeautifulSoup4, Google Play Scraper

```

---

### نصيحة سريعة قبل إضافته:
* بعد ما تنشري التطبيق على **Streamlit Community Cloud** ويطلع لك الرابط المباشر للتطبيق (مثل `[https://your-app.streamlit.app](https://your-app.streamlit.app)`)، أضيفي قسماً صغيراً في أعلى الـ `README.md` بعنوان `## 🌐 Live Demo` وحطّي فيه رابط التطبيق المباشر عشان أي زائر أو صاحب عمل يجربه بنقرة واحدة!

```
