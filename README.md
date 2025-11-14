# AI---FEATURE-ENGINEERING

# Feature Engineering on Canadian Election Results 🇨🇦

## 📌 Project Overview
This repository contains a Data Science project focused on **Feature Engineering** and data preprocessing. The goal is to transform a raw dataset of Canadian Federal Election results into a clean, structured format suitable for machine learning models (classification or regression).

The project demonstrates key techniques such as categorical encoding, feature scaling, dimensionality reduction (PCA), and feature selection.

## 📂 Dataset
- **Name:** Canadian Federal Election Results (`Results.csv`)
- **Source:** [Open Government Canada / Kaggle / Provided by Instructor]
- **Description:** The dataset contains poll-by-poll results, including election identifiers, electoral district numbers, polling station IDs, ballot sequence numbers, and vote counts for candidates.
- **Size:** ~2.7 million rows (A sample of 10,000 rows was used for the analysis).

## 🛠️ Technologies Used
- **Python 3.x**
- **Pandas** (Data Manipulation)
- **Scikit-learn** (Preprocessing, PCA, Feature Selection)
- **Matplotlib & Seaborn** (Data Visualization)
- **Google Colab** (Notebook Environment)

## ⚙️ Feature Engineering Steps
The following transformations were applied to the raw data:

1.  **Data Cleaning:**
    - Renamed complex bilingual columns to simplified English names (e.g., `vote_count`, `event_number`).
    - Verified the dataset for missing values (none found in the clean version).

2.  **Categorical Encoding:**
    - Applied **Label Encoding** to high-cardinality features (`election_id`, `electoral_district_id`, `polling_station_id`) to convert text IDs into numeric values.

3.  **Feature Scaling:**
    - Applied **StandardScaler** (Z-score normalization) to numeric features (`event_number`, `ballot_sequence`, `vote_count`). This ensured that features with large ranges (like years) did not dominate the model.

4.  **Dimensionality Reduction:**
    - Implemented **Principal Component Analysis (PCA)** to compress the feature set into 2 principal components, which retained approximately 99% of the variance.

5.  **Feature Selection:**
    - Analyzed feature relationships using a **Correlation Matrix**.
    - Used **SelectKBest** to statistically identify the top 3 features most relevant to predicting vote counts.

## 📊 Key Observations
- The dataset showed strong internal structure, allowing for significant dimensionality reduction without losing information.
- Scaling was critical; without it, the `event_number` (year) disproportionately influenced the variance analysis.
- Statistical selection confirmed that `ballot_sequence` and `district_id` are strong predictors for vote distribution.

## 🚀 How to Run
1.  Clone this repository:
    ```bash
    git clone <your-repo-link>
    ```
2.  Open the `.ipynb` file in **Google Colab** or Jupyter Notebook.
3.  Upload the `Results.csv` file to the runtime environment.
4.  Run all cells to reproduce the analysis.

## ⚖️ Ethical Discussion
This project includes a discussion on **Algorithmic Bias**, specifically regarding the use of sensitive attributes like Gender or Marital Status in predictive models (e.g., for employee attrition).

**Mitigation Strategies Discussed:**
- **Exclusion:** Removing protected attributes from training data.
- **Reweighting:** Adjusting sample weights to correct historical imbalances.
- **Adversarial Training:** Using adversary networks to remove demographic information from latent representations.

---
**Author:** [Your Name]
**Date:** [Current Date]
