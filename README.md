# 💕 Intent Prediction & Algorithmic Alignment in Online Dating
[![Topic](https://img.shields.io/badge/Topic-Product_Strategy-blue)](https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment-in-Online-Dating)
[![Method](https://img.shields.io/badge/Method-Supervised_ML_%7C_Unsupervised_NLP_%7C_Causal_Inference-green)](https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment-in-Online-Dating)
[![Tools](https://img.shields.io/badge/Tools-Python-orange)](https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment-in-Online-Dating)

### **Project Overview**
[**View the Project Slides (PDF)**](./Francemone_Intent_Prediction_and_Algorithmic_Alignment_in_Online_Dating.pdf)

This project moves beyond standard demographic filtering to build a **Multi-Modal Intent Framework** in online dating. A critical friction point in online dating is mismatched intent (e.g., Wants Kids vs. Child-free), which leads to low-quality dates and churn.

Using a dataset of ~60,000 profiles, I developed a three stage analytical framework combining **Supervised Learning** (Gradient Boosting), **Unsupervised NLP** (LDA), and **Causal Inference** (Propensity Score Matching) to isolate drivers of family planning intent.

---

### **Key Findings & Strategic Insights**

#### **1. Demographics Provide a Strong Baseline (79% Accuracy)**
* **Age**, **Sexuality**, and **Religion** are the primary gatekeepers of family planning. However, demographic models struggle to differentiate between **Lifestyle Choice** (child-free by choice) and **Life Stage** (not ready yet).

#### **2. Language is a Behavior: 5 Distinct Personas**
<img src="notebooks/lda_viz.png" alt="Topic Modeling Visualization" width="75%">
By analyzing user essays, I identified five robust psychographic clusters that cut across demographics:
* **The Artist:** Creative, non-traditional.
* **The Techie:** Niche interests, analytical.
* **The Socialite:** Community-focused, extraverted.
* **The Professional:** Career-focused, stable.
* **The Romantic:** Intimacy-focused, emotional.

#### **3. Causal Drivers vs. Proxy Signals**
Using **Propensity Score Matching (PSM)**, I separated causal drivers from correlations:
* **The Socialite Effect (+18.46% Lift):** Validated as a robust causal driver. Users who signal social behaviors are fundamentally more driven toward family building.
    * *Recommendation:* Elevate social keywords (dinner, bar, events) as high-confidence proxies.
* **The Techie Divergence (-19.76% Lift):** Validated as a robust deterrent. This persona represents a distinct, competing life goal.
    * *Recommendation:* Implement hard segmentation; do not nudge these users toward family tracks.
* **The Romantic Null (-1.79% Lift):** Seeking love does not mean seeking family. Users using highly romantic language show zero causal increase in desire for children.
    * *Recommendation:* Decouple romance from parenthood; separate intimacy signals from family building signals.

---

### **Methodology**

* **Data Source:** Anonymized profile essays and demographic flags from ~60,000 users (OkCupid open dataset).
* **Modeling Strategy:**
    * **Supervised Learning (XGBoost):** To predict binary intent labels ("Wants Kids" vs. "Does Not").
    * **Unsupervised Learning (LDA):** To extract latent psychographic topics (Personas) from unstructured text.
    * **Causal Inference (Propensity Score Matching):** To estimate the "lift" of specific personas on family planning intent, controlling for demographics.
* **Tools:** Python (pandas, scikit-learn, gensim, XGBoost).

---

### **Repository Structure**
This repository separates data, model artifacts, and analysis logic.

```text
/Intent-Prediction-and-Algorithmic-Alignment
│
├── /notebooks
│   ├── Intent_Prediction_and_Algorithmic_Alignment.ipynb      <-- Main analysis notebook
│   ├── Intent_Prediction_and_Algorithmic_Alignment.html
│   └── lda_viz.png
│
├── /models
│   ├── dictionary_frozen.gensim                               <-- LDA model artifacts
│   ├── lda_model_frozen.gensim
│   ├── lda_model_frozen.gensim.expElogbeta.npy
│   ├── lda_model_frozen.gensim.id2word
│   └── lda_model_frozen.gensim.state
│
├── /data
│   └── (Excluded from repo due to size)                       <-- Raw profile data
│
├── requirements.txt                                           <-- Dependencies for reproduction
└── Francemone_Intent_Prediction_and_Algorithmic_Alignment.pdf <-- Summary Slide Deck
```

---

### **Reproducibility**

**Prerequisites:**
To reproduce this analysis, you will need the packages listed in `requirements.txt`.

**Installation:**
1.  Clone the repository:
    ```bash
    git clone https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment-in-Online-Dating.git
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  **Run the Analysis:**
    Navigate to `notebooks/` and launch the Jupyter Notebook.

---

### **My Role**
**Lead Data Scientist & Researcher**
* Built and tuned the XGBoost predictive model for intent classification.
* Engineered the end-to-end NLP pipeline (LDA Topic Modeling) to extract user personas.
* Applied Propensity Score Matching (PSM) to isolate causal drivers of family planning intent.
