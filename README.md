# 🩺 Medical Insurance EDA (Healthcare Premium Analysis)

**Goal:** Explore the insurance dataset to understand how demographic and lifestyle factors (age, BMI, children, smoker, region, sex) relate to **insurance charges**, and lay the groundwork for a predictive model.

## 📦 Dataset
- `insurance.csv`
  - `age`, `sex`, `bmi`, `children`, `smoker`, `region`, `charges`
> If redistribution isn’t allowed, remove the file and link to the source instead.

## 🔍 What I did (Steps & Observations)
1) **Load & Inspect**
   - Checked shape and dtypes; validated categorical vs numeric fields.
   - *Observation:* (e.g.) No ID column; target is `charges`.

2) **Missing Values**
   - Verified nulls and applied strategy (drop/impute if needed).
   - *Observation:* (e.g.) No missing values found / Imputed BMI median.

3) **Univariate & Bivariate EDA**
   - Count plots for `sex`, `smoker`, `region`; histograms for `age`, `bmi`, `charges`.
   - Scatter/strip plots: `age` vs `charges`, `bmi` vs `charges` (hue=`smoker`).
   - *Observation:* (e.g.) Smokers show markedly higher charges across ages.

4) **Feature ↔ Feature**
   - Pairwise comparisons (e.g., `bmi` vs `age`; boxplots by `children`, `region`).
   - *Observation:* (e.g.) Higher BMI associates with higher charges; effect amplified in smokers.

5) **Ageing vs Premium**
   - Grouped by smoker status and age bins to examine charge trends.
   - *Observation:* (e.g.) Charges increase with age for both groups; slope steeper for smokers.

6) **Ready for Modeling**
   - Encoded categoricals; considered log-transform for skewed `charges`.
   - Split train/test and (optionally) baseline linear model for sanity check.

## 📊 Key Visuals
See `reports/figs/`:
- `charges_vs_age.png`
- `charges_vs_bmi_by_smoker.png`
- `charges_by_region.png`
- `count_smoker.png`

## 🛠️ Tech
- Python, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn
- Jupyter Notebook

## ▶️ How to run
```bash
git clone https://github.com/anchalsingh154/medical-insurance-eda.git
cd medical-insurance-eda
python -m venv .venv
# Activate the venv (Windows: .venv\Scripts\activate | macOS/Linux: source .venv/bin/activate)
pip install -r requirements.txt
jupyter notebook notebooks/Insurance\ Data\ Analysis_SourceCode.ipynb
