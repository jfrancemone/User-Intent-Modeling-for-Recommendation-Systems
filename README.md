# 🤖 Intent Prediction & Algorithmic Alignment
[![Topic](https://img.shields.io/badge/Topic-NLP_%26_Machine_Learning-blue)]()
[![Method](https://img.shields.io/badge/Method-XGBoost_%7C_Causal_Inference-green)]()
[![Status](https://img.shields.io/badge/Status-Project_Complete-orange)]()

### **Project Overview**
[**View the Project Slides (PDF)**](./Francemone_Intent_Prediction_and_Algorithmic_Alignment.pdf)

This project moves beyond standard demographic filtering to build a **Multi-Modal Intent Framework**. A critical friction point in online dating is mismatched intent (e.g., "Wants Kids" vs. "Child-free"), which leads to low-quality dates and churn.

Using a dataset of ~60,000 profiles, I developed a three-tiered analytical framework combining **Supervised Learning** (Gradient Boosting), **Unsupervised NLP** (LDA), and **Causal Inference** (Propensity Score Matching) to isolate the true drivers of family planning intent.

---

### **Key Findings & Strategic Insights**

#### **1. Demographics Provide a Strong Baseline (80% Accuracy)**
**Age**, **Sexuality**, and **Religion** are the primary gatekeepers of family intent. However, demographic models struggle to differentiate between **"Lifestyle Choice"** (child-free by choice) and **"Life Stage"** (not ready yet).

#### **2. Language is a Behavior: 5 Distinct Personas**
By analyzing user essays, I identified five robust psychographic clusters that cut across demographics:
* **The Artist:** Creative, non-traditional.
* **The Techie:** Niche interests, analytical.
* **The Socialite:** Community-focused, extraverted.
* **The Professional:** Career-focused, stable.
* **The Romantic:** Intimacy-focused, emotional.

#### **3. Causal Drivers vs. Proxy Signals**
Using **Propensity Score Matching (PSM)**, I separated causal drivers from simple correlations:
* **The Socialite Effect (+18.46% Lift):** Validated as a robust causal driver. Users who signal social behaviors are fundamentally more driven toward family building.
    * *Recommendation:* Elevate social keywords (dinner, bar, events) as high-confidence proxies.
* **The Techie Divergence (-19.76% Lift):** Validated as a robust deterrent. This persona represents a distinct, competing life goal.
    * *Recommendation:* Implement hard segmentation; do not nudge these users toward family tracks.
* **The Romantic Null (-1.79% Lift):** Seeking love does not mean seeking family. Users using highly romantic language show zero causal increase in desire for children.

---

### **Repository Structure**
This repository separates data, model artifacts, and analysis logic.

```text
/Intent-Prediction-Analysis
│
├── /notebooks
│   └── Intent_Prediction_Analysis.ipynb  <-- Main analysis notebook
│
├── /models
│   └── (Excluded from repo due to size)  <-- LDA model artifacts (.gensim)
│
├── /data
│   └── (Excluded from repo for privacy)  <-- Raw profile data
│
├── requirements.txt                      <-- Dependencies for reproduction
└── Francemone_Intent_Prediction.pdf      <-- Summary Slide Deck****
