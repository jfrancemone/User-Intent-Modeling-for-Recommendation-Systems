# Intent Prediction & Algorithmic Alignment
## 📊 Project Overview
[**View the Project Slides (PDF)**](./Francemone_Intent_Prediction_and_Algorithmic_Alignment.pdf)
### Reducing User Friction through Multi-Modal Intent Analysis

**Techniques:** Supervised  Gradient Boosting, Unsupervised NLP (LDA), Causal Inference (Propensity Score Matching)

**Tools:** Python, Pandas, SpaCy, Scikit-Learn, SHAP

---

## Executive Summary

### The Challenge: Reducing Algorithmic Friction
A critical friction point in online dating is mismatched intent. Matching users with conflicting relationship goals, specifically around family planning (e.g., "Wants Kids" vs. "Child-free"), leads to low-quality dates, user churn, and fatigue.

### The Approach
This project moves beyond standard demographic filtering to build a **Multi-Modal Intent Framework**. Using a dataset of ~60,000 profiles, I developed a three-tiered analytical framework:
1.  **Predictive Modeling (Gradient Boosting Classifiers):** Estimating baseline predictability of family intent using structured demographic and lifestyle data.
2.  **Unsupervised NLP (LDA):** Extracting latent psychographic personas from open-ended user essays for user segmentation.
3.  **Causal Inference (Propensity Score Matching):** Isolating the **causal impact** of these personas on family planning, independent of other key family planning drivers.

## Key Findings & Strategic Insights

### 1. Demographics Provide a Strong Baseline (80% Accuracy)
**Age**, **Sexuality**, and **Religion** are the primary gatekeepers of family intent. However, demographic models struggle to differentiate between **"Lifestyle Choice"** (e.g., child-free by choice) and **"Life Stage"** (e.g., not ready yet). Identifying this nuance required analyzing the unstructured text data.

### 2. Language is a Behavior: 5 Distinct Personas
By analyzing user essays, I identified five robust psychographic clusters that cut across demographics:
* **The Artist:** Creative, non-traditional.
* **The Techie:** Niche interests, analytical.
* **The Socialite:** Community-focused, extraverted.
* **The Professional:** Career-focused, stable.
* **The Romantic:** Intimacy-focused, emotional.

### 3. Causal Drivers vs. Proxy Signals
Using **Propensity Score Matching (PSM)** and **Sensitivity Analysis**, I separated causal drivers from correlations:

* **The Socialite Effect (+18.46% Lift):** Validated as a robust causal driver (Gamma = 2.3). Even after controlling for demographics, users who signal social behaviors are fundamentally more driven toward family building.
    * *Recommendation:* Elevate social keywords (dinner, bar, events) as high-confidence proxies for family intent.
* **The Techie Divergence (-19.76% Lift):** Validated as a robust deterrent (Gamma = 2.1). This persona represents a distinct, competing life goal focused on technological and media-related interests.
    * *Recommendation:* Implement hard segmentation. Do not nudge these users toward family tracks; optimize for shared-interest matching instead.
* **The Romantic Null (-1.79% Lift):** Seeking love does not mean seeking family. Users using highly romantic language show zero causal increase in desire for children (p = 0.22).
    * *Recommendation:* Decouple algorithmic weighting of "Romance" and "Family" wording to prevent expectation mismatch.

### Conclusion
This analysis confirms that **psychographic personas are not just descriptive, they are predictive drivers of user intent.** Integrating NLP-derived signals can significantly reduce false-positive matches, moving the platform from simple interest-based relationships to deep intent-based relationships.

---

## Project Structure

This repository is organized to separate data, model artifacts, and analysis logic.

* `notebooks/`: Contains the main analysis notebook (`Intent_Prediction_and_Algorithmic_Alignment.ipynb`).
* `models/`: (Not tracked in repo) Stores the trained LDA model (`.gensim`) and dictionary artifacts.
* `data/`: (Not tracked in repo) Stores raw profile data and processed pickle files.

## Getting Started

### Prerequisites
To reproduce this analysis, you will need the packages listed in `requirements.txt`.

### Installation
1.  Clone the repository:
    ```bash
    git clone [https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment.git](https://github.com/jfrancemone/Intent-Prediction-and-Algorithmic-Alignment.git)
    ```
2.  Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3.  Run the notebook:
    Navigate to the `notebooks/` directory and launch Jupyter Lab or Jupyter Notebook.
