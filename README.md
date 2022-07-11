# Heart-Transplant-Rankings

Code files corresponding to the 'The Accuracy of Initial US Heart Candidate Rankings'. <br />
KP wrote the Python and R files. <br />
KZ tested and updated the code and is currently maintaining the Github. <br />

Files should be run in this order:

### 1. Survival_Data_Initial_Processing_UC.ipynb (Python 3.8.8)
Uses raw SRTR data and performs initial cleaning procedures: inclusion-exclusion criteria, derived variables. Splits data into the early cohort/training data from 2010-2017 and the late cohort/test data from 11/2018 to 3/2020.

### 2. Survival_Data_Descriptive_Stats_UC.ipynb (Python 3.8.8)
Derives descriptive statistics for Table 1. Log-rank and chi-squared tests are used to determine differences. Optional file.

### 3. Survival_Data_Output_for_R_UC.ipynb (Python 3.8.8)
Normalizes data, adds status ranking, saves data to csv files for processing in R.

### 4. Waitlist_Survival_Data_Processing.Rmd (R 4.2.3)
Reads in csv files, imputes missing data using mice.

### 5. CPH_and_RF_Calculations.Rmd (R 4.2.3)
Runs the primary models, Cox Proportional Hazards and Random Survival Forest, with and without treatments. Includes hyperparameter tuning.

### 6. Variable_importance.Rmd (R 4.2.3)
Calculates single and joint variable importance in the Random Survival Forest models.

### 7. 6statusC.Rmd (R 4.2.3)
Calculates Harrell's c-indices (**Harrell et al, Evaluating the yield of medical tests, *JAMA*, 1982**) based on the 6-status ranking at listing for the late cohort, treating lower status as equivalent to a higher risk prediction. Bootstrapping is used to calculate the confidence intervals.

### 8. Brier_scores.Rmd (R 4.2.3)
Calculates Brier scores (**Brier, Verification of forecasts expressed in terms of probability, *Mon Weather Rev*, 1982**).

### 9. Bootstrapping_c_indices_Harrells.Rmd (R 4.2.3)
Uses bootstrapping to find confidence intervals for Harrell's c-indices.

### 9. Bootstrapping_c_differences.Rmd (R 4.2.3)
Uses bootstrapping to find confidence intervals for Wald tests of differences.
