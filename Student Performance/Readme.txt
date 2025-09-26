# Student Performance Visualization Project

##  Project Overview
The project examines student academic performance trends based on an exam score and demographic data dataset.
The objective is to exercise a three-step workflow — **ingest → process → analyze** — and generate understandable, reproducible visualizations.
Five research questions are limited to specific domains of investigation where data cleaning, visualization, and interpretation provide the answer.

---
## Dataset
- **Source**: Students Performance dataset (CSV file provided).  
- **Size**: ~1,000 records, each containing exam scores and student attributes.  
- **Attributes**:
  - Gender  
  - Race/ethnicity  
  - Parental level of education  
  - Lunch type (standard vs free/reduced)  
  - Test preparation course (completed vs none)
- Scores in **math**, **reading**, and **writing**  

The raw dataset is stored in:  

---

## ⚙️ Workflow

### 1. Ingestion
- Imported the dataset using `pandas`.  
- Verified the shape, columns, and data types.  
- Checked for missing values (none were found).  

### 2. Preprocessing
- Cleaned column names where necessary.
- Assigned a new variable `overall_avg = (math + reading + writing) / 3` to be used later.
- Converted all scores to numeric format.

### 3. Analysis & Visualization
Five of the questions of study were answered using visualizations:

1. **V1 — Math vs reading gender differences**
   - Side-by-side boxplots by gender.

2. **V2 — Test prep impact on math**
- Comparison of math scores for students who completed vs didn't complete test prep.

3. **V3 — Type of lunch and average performance**
   - Average overall score by type of lunch grouped bar chart.

4. **V4 — Subject correlations**
   - Correlations between math, reading, and writing heatmap.

5. **V5 — Math vs reading with trend lines by test prep**
   - No-prep vs prep groups regression lines scatterplot.

All the plots are **800×600 px, 300 DPI** with appropriate titles, axis labels, legends, and legible ticks.


