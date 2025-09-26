# Frailty Dataset Workflow

## Project Description
This project explores a small dataset of 10 female participants where frailty is studied in relation to grip strength. The idea is to build a simple three-step workflow (ingest → process → analyze) to show how raw health data can be cleaned, transformed, and summarized in a reproducible way.

Frailty is a qualitative condition (yes/no), while grip strength is measured in kilograms. Since grip strength is often used as an indicator of frailty, we examine whether reduced grip strength relates to higher frailty scores.

---

## Dataset
- **Source**: manually collected table (10 participants)  
- **File**: `data/frailty_data.csv`  
- **Columns**:  
  - `Height_in` (inches)  
  - `Weight_lb` (pounds)  
  - `Age_yr` (years)  
  - `Grip_kg` (kilograms)  
  - `Frailty` (Y/N)

---

## Steps Followed

### 1. Ingestion
- Saved the original dataset as `frailty_data.csv` in the `data/` folder.  
- Loaded it into a Pandas DataFrame using Jupyter Notebook.  
- Kept the raw file unchanged so results are reproducible.

### 2. Processing
- Converted units:  
  - Height → meters (`Height_m = Height_in * 0.0254`)  
  - Weight → kilograms (`Weight_kg = Weight_lb * 0.45359237`)  
- Created new features:  
  - `BMI = Weight_kg / (Height_m ** 2)` (rounded to 2 decimals)  
  - `AgeGroup` (categories: `<30`, `30–45`, `46–60`, `>60`)  
- Encoded categorical variables:  
  - Frailty: `Y = 1`, `N = 0` → `Frailty_binary`  
  - One-hot encoding for AgeGroup (e.g., `AgeGroup_<30`, `AgeGroup_30–45` etc.)  
- Exported the processed data to:  
  `data/processed/frailty_data_processed.csv`

### 3. Analysis
- Generated summary statistics (mean, median, standard deviation) for numeric features.  
- Measured correlation between `Grip_kg` and `Frailty_binary`.  
- Wrote the results into `reports/findings.md` with both the numbers and a short interpretation.

---

## Results
- **Sample size**: 10 participants.  
- **Correlation**: Grip strength and frailty showed a moderate negative relationship.  
  → Lower grip strength values were more often linked with frailty = "Yes".  
- **Summary statistics** (heights, weights, BMI, grip, etc.) are included in `reports/findings.md`.


