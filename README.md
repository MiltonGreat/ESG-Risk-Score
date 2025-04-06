# ESG Score Prediction Project

![screenshot-localhost_8888-2025 04 06-10_31_16](https://github.com/user-attachments/assets/92e72f53-0bbf-4fc4-92f2-f4c5227792bd)

### Project Overview

This project analyzes Environmental, Social, and Governance (ESG) scores for companies, building a machine learning model to predict total ESG scores based on component scores (E, S, G) and other derived features.

### Key Steps

1. Data Loading & Exploration
- Loaded dataset with pandas.
- Checked distributions, missing values, and correlations.

2. Data Preprocessing
- Handled missing values: Filled industry with "Unknown," dropped logo and weburl.
- Converted categorical grades (e.g., "AAA" → 7) for numerical analysis.

Engineered features:
- esg_balance: Relative weight of environmental vs. social scores.
- esg_variation: Standard deviation across E/S/G scores.

3. Model Building (Random Forest)
- Pipeline: Preprocessing (OneHotEncoder for industries) + RandomForestRegressor.
Metrics:
- R² = 0.99 (explains 99% of variance).
- RMSE = 14.98 (error ~1.6% of score range).

4. Insights & Interpretation
- Total scores are highly predictable from E/S/G components.
- Environmental score dominates (0.96 correlation).
- Suggests total_score ≈ weighted sum of E + S + G.

### Key Findings

- The model achieves near-perfect accuracy (R² = 0.99, RMSE = 14.98).
- Environmental score (0.96 correlation) is the strongest predictor of total ESG score.
- Results suggest that total ESG scores may be a weighted composite of E, S, and G sub-scores.

### Conclusion

This project demonstrates that ESG total scores are highly predictable from their underlying components, making ML overkill if a simple formula exists. However, the analysis provides valuable insights into ESG scoring dynamics, highlighting the dominance of environmental factors in overall ratings.

#### Future work could focus on:
- Interpretability: Explaining scoring weightings to stakeholders.
- Anomaly Detection: Identifying companies where the formula doesn’t align.
- Policy Impact: Assessing whether the heavy weighting on environmental factors aligns with corporate sustainability goals.
    
### Source

[Public Company ESG Ratings Dataset from Kaggle](https://www.kaggle.com/datasets/alistairking/public-company-esg-ratings-dataset)
