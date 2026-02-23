Predicting Annual Compensation from Stack Overflow Survey Data

Short, end-to-end ML pipeline to predict annual compensation using Stack Overflow Developer Survey data. The project covers data cleaning, feature engineering (multi-select encoding, target normalization), model training with XGBoost, hyperparameter tuning, and evaluation.

---

PROJECT MOTIVATION
Compensation prediction is challenging due to global economic disparities, missing high-impact features (seniority, company size, negotiation), and skewed distributions. This project provides a robust baseline, documents findings, and highlights improvement paths for realistic performance.

TECH STACK / LIBRARIES
- Python 3.10+
- pandas, numpy
- seaborn, matplotlib
- scikit-learn
- xgboost
- jupyter

SETUP & INSTALLATION
1) Create and activate environment (conda or venv)
   conda create -n salary-ml python=3.10 -y
   conda activate salary-ml
   # or: python -m venv .venv && source .venv/bin/activate

2) Install dependencies
   pip install -U pandas numpy seaborn matplotlib scikit-learn xgboost jupyter

3) (Optional) Freeze
   pip freeze > requirements.txt

4) Launch notebook
   jupyter notebook

Place survey_results_public.csv in the data/ folder (or update the path in the notebook).

REPOSITORY STRUCTURE (SUGGESTED)
.
├─ data/
│  └─ survey_results_public.csv
├─ notebooks/
│  └─ 01_salary_modeling.ipynb
├─ src/
│  └─ features.py
├─ README.txt
└─ LICENSE

USAGE
1) Open notebooks/01_salary_modeling.ipynb
2) Run cells in order:
   - Load & inspect data
   - Feature cleaning (multi-select counts, top-N binary encoding)
   - Country → continent mapping (optional)
   - Outlier trimming (top 1%)
   - Log-transform target
   - Train/valid/test split
   - Preprocessing (OrdinalEncoder + StandardScaler)
   - XGBoost + GridSearchCV
   - Evaluation (R², MAPE)

Example (already in the notebook):
- Build pipeline (preprocess + XGBoost)
- Grid search hyperparameters
- Evaluate on validation and test sets

FEATURES
- Multi-select parsing & Top-N binary encoding (Languages, Tools, Databases)
- Semicolon-count features for multi-choice columns
- Custom missing value imputation rules
- Outlier trimming by quantile
- Log-target transformation for skew reduction
- Multicollinearity filter (correlation-based drop)
- XGBoost pipeline with grid search
- Train/Validation/Test protocol

RESULTS (CURRENT BASELINE)
- Validation: R² ≈ 0.19, MAPE ≈ 3749%
- Test: R² ≈ 0.19, MAPE ≈ 1433%
Interpretation: R² shows ~19% variance explained; MAPE is unstable for salary prediction due to small incomes and extreme outliers. Constraints include country-driven disparities, missing key determinants, and noisy categorical features.

IMPROVEMENT ROADMAP
- Normalize salaries by PPP (Purchasing Power Parity) to remove country bias
- Prefer country-level encoding (target/cat encoding) over continent grouping
- Replace MAPE with MAE or RMSLE for stable error measurement
- Try CatBoost Regressor for high-cardinality categoricals
- Engineer interaction features (Age × YearsCode, WorkExp × DevType)
- Consider segmented modeling (by role level or region)

LICENSE
MIT License (or update per organizational policy).

AUTHORS & ACKNOWLEDGMENTS
- Author: Yuşa Çalık
- Thanks: Vodafone Data&AI team peers; Stack Overflow survey team for the dataset

CONTACT
- Email: yusacalik@gmail.com
- LinkedIn: https://www.linkedin.com/in/yusacalik
- GitHub Repo: https://github.com/your-org/your-repo

BLOG POST
Publish an overview covering:
- Problem framing & dataset caveats
- Key feature engineering ideas
- Baseline results & why MAPE fails here
- Improvement roadmap (PPP normalization, CatBoost, better metrics)
Add link once published: https://your-blog-platform.com/your-post