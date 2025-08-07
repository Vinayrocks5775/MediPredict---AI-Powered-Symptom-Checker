
# 🩺 MediPredict: AI-Powered Medical Disease Prediction

**MediPredict** is a cloud-deployed, AI-driven platform for predicting likely diseases based on symptom severity. It provides actionable health recommendations and interacts with users via an intelligent rule-based chatbot. Built using Azure services and machine learning best practices, MediPredict offers a secure, scalable, and real-time solution for healthcare prediction.

## 🔍 What MediPredict Does

- ✅ Predicts **top 3 diseases** from 100+ symptoms using ML models.
- 🧠 Provides **precautions** and recommends **doctor types**.
- 💬 Includes a **rule-based chatbot** for 200+ health queries.
- 📄 Allows **PDF download** of results for clinical use or record-keeping.
- 📊 Supports **model experimentation** and evaluation through notebooks.
- 🌐 Hosted on **Azure App Service**, with **end-to-end orchestration** via Azure Data Factory and Databricks.

## 🧠 Machine Learning Pipeline

MediPredict follows the **Medallion Architecture** to ensure a clean and modular ML workflow:

1. **Bronze Layer**:  
   - Raw zipped data extracted from Google Drive using **Databricks Notebook 1**.  
   - Stored in **Azure Blob Storage**.

2. **Silver Layer**:  
   - Cleaned, transformed, and encoded data using **Notebook 2**.  
   - Processed data written back to Blob.

3. **Gold Layer**:  
   - ML models trained using **Notebook 3** on cleaned data.  
   - Best models and encoders saved as `.pkl` files for prediction.

> 🧩 Notebooks are orchestrated using **Azure Data Factory Pipelines** to ensure smooth, automated execution.

## 🛠️ Tech Stack

| Area             | Tools |
|------------------|-------|
| Programming      | Python 3.8+ |
| ML Libraries     | scikit-learn, XGBoost, Pandas, NumPy |
| Web Framework    | Streamlit |
| PDF Generation   | FPDF |
| Chatbot Logic    | Rule-based Python |
| ML Training      | Jupyter Notebooks |
| Deployment       | Azure App Service |
| Data Pipeline    | Azure Data Factory + Azure Databricks |
| Storage          | Azure Blob Storage |
| Version Control  | GitHub |

## 🗂️ Project Structure

```
├── data/         # Raw and processed datasets
├── notebooks/    # EDA, training, evaluation
├── src/          # Streamlit app, chatbot, ML logic
├── models/       # Trained models (.pkl), encoders
├── features/     # Feature maps and symptom clusters
├── outputs/      # Plots, reports, results
├── requirements.txt
└── README.md
```

## ✨ Key Features

- 🎨 **Modern UI**: Glassmorphism design, intuitive stepper layout.
- 🧠 **Symptom Severity Input**: User-friendly sliders and auto-suggestions.
- 📊 **Prediction Results**: Probabilities, mapped precautions, doctor suggestions.
- 💾 **PDF Export**: Save/share predictions via downloadable report.
- 💬 **Chatbot**: Rule-based system with fallback advice to general physician.
- 🔁 **Retrainable Models**: Notebooks support retraining and tuning with new data.
- ☁️ **Azure Deployed**: Fast, scalable access with secure cloud hosting.

## ▶️ How to Use MediPredict

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Train or Explore Models
- Run notebooks in `/notebooks` for EDA and model evaluation.

### 3. Launch the App
```bash
streamlit run src/app.py
```

## 🚀 Azure Deployment Workflow

MediPredict uses a cloud-first architecture, optimized for automation and scalability:

1. **Data Flow**
   - ZIP files from Google Drive extracted via **Databricks Notebook 1** → stored in **Blob Storage (Bronze)**.
   - Cleaned & encoded in **Notebook 2** → stored in **Silver** layer.
   - ML models trained in **Notebook 3** → saved as `.pkl` files in **Gold** layer.

2. **Automation**
   - All notebooks connected and executed using **Azure Data Factory** pipelines.

3. **Code to Deployment**
   - Final code, models, and assets pushed to **GitHub**.
   - GitHub linked to **Azure App Service**, which pulls and deploys the Streamlit application.

4. **Hosting**
   - App is live and accessible via a public **Azure URL**, with all assets served securely.

## 📎 Requirements

- Python 3.8+
- pip
- See `requirements.txt` for full dependency list

## 📡 Live App

🔗 [https://your-azure-url](https://your-azure-url)

## 📌 Summary

MediPredict integrates machine learning, clean architecture, and Azure cloud services into a fully functional and scalable medical prediction app. It's an end-to-end demonstration of MLOps, cloud deployment, and real-time healthcare AI.
