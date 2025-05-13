# 🚀 Project Objective

Detect subscription and contract management anomalies for insurance policies.

## 1. Business Context

The Internal Control Department at Allianz must ensure compliance with subscription and contract management rules (Individual, Business, Health, Life, etc.).
Your mission: simulate a real case by developing an end-to-end anomaly detection prototype that:

* Automatically checks the compliance of new contracts (missing attributes, out-of-range premiums, incompatible coverages, etc.).
* Flags potentially fraudulent behaviors (abnormal amounts, unusual subscription frequency, sudden cancellations).

## 2. Project Goals

1. **Data collection & simulation**

   * Generate a synthetic dataset (10,000 contracts) with:

     * Client ID, product type, subscription date, premium amount, coverages, location, claim status.
   * Or leverage an open-source “insurance” dataset.

2. **Exploration & feature engineering**

   * Clean and consolidate data (handle missing values, categorical encoding, normalization).
   * Extract business indicators:

     * Contract age, subscription–claim delay, cancellation frequency, premium-to-claim ratio.

3. **CPU-only anomaly detection**

   * **Unsupervised** approaches: Isolation Forest, One-Class SVM, dense Autoencoder (PyTorch CPU).
   * **Statistical** methods: Mahalanobis distance, DBSCAN clustering.
   * Compare recall and precision on a labeled subset (5% injected anomalies).

4. **Evaluation & tuning**

   * Metrics: ROC–AUC, Precision\@K, F1-score for rare anomalies.
   * Hyperparameter optimization: number of trees, encoder size, detection thresholds.

5. **Explainability & reporting**

   * Use SHAP for feature contributions.
   * Visualizations: distributions, score curves, heatmaps.
   * Static dashboard with Plotly + Dash (CPU-only).

6. **Packaging & REST API**

   * Docker + FastAPI (Uvicorn):

     * Endpoint `/predict` accepting a contract JSON, returning an anomaly score + explanations.
   * Swagger documentation.

## 3. Targeted Skills

* Advanced anomaly detection (Autoencoder, Isolation Forest, Mahalanobis).
* CPU-only machine learning (PyTorch optimization).
* Explainable AI (SHAP).
* Lightweight MLOps (Docker, FastAPI).
* Data engineering (simulation, pipelines).

## 4. Technical Constraints

* **100% CPU**.
* **Zero cost** (open source).
* **Local & reproducible**.

## 5. One-week Plan

|               Day              | Tasks                                    |
| :----------------------------: | :--------------------------------------- |
|              **1**             | Data generation & ingestion              |
| Repo structure & README setup. |                                          |
|              **2**             | Cleaning & feature engineering           |
|          EDA notebook.         |                                          |
|              **3**             | Baselines: Isolation Forest, Mahalanobis |
|       Initial evaluation.      |                                          |
|              **4**             | PyTorch CPU Autoencoder                  |
|     Training & validation.     |                                          |
|              **5**             | Hyperparameter tuning                    |
|        Advanced metrics.       |                                          |
|              **6**             | Explainability (SHAP, visualizations)    |
|         Dash dashboard.        |                                          |
|              **7**             | Docker & FastAPI                         |
|     Final report & slides.     |                                          |

## 6. Deliverables

* Structured GitHub repository.
* Complete Jupyter notebook.
* Exportable Dash dashboard.
* Docker image + Swagger API.
* Summary document + slides.
