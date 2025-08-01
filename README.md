# Dowdle Analytics Capstone Introduction
This is the project repository for a machine learning pipeline to predict procurement compliance based on real-world procurement KPI data. This project uses historical purchase order data including pricing, delivery, and defect metrics to predict whether an order will be compliant with supplier agreements. By building predictive models using procurement KPIs, the goal is to support strategic sourcing and vendor performance monitoring. 

## Project Resources
[Clickable link to my cleaned data file](https://github.com/Bdowdle4/Dowdle_Analytics_Capstone/blob/main/Data/cleaned_procurement_data.csv)

[Data Source](https://www.kaggle.com/datasets/shahriarkabir/procurement-kpi-analysis-dataset)

[GitHub Repository](https://github.com/Bdowdle4/Dowdle_Analytics_Capstone)

[Overleaf Report](https://www.overleaf.com/read/bszyhdxsnrsf#70bd68)

[Clickable link to my report PDF](https://github.com/Bdowdle4/Dowdle_Analytics_Capstone/blob/main/Report/Dowdle_44688_Capstone.pdf)

[Clickable link to my visualizations](https://github.com/Bdowdle4/Dowdle_Analytics_Capstone/tree/main/Visualizations)

****

## Project Workflow
- **Cleans & pre-processes** 777 PO records (2022–2023) from 5 suppliers and ending with 758 PO records 
- **Explores** relationships via EDA with trend lines, distributions, and correlations  
- **Builds & tunes** Logistic Regression and Random Forest models (same models were retrained with fewer features selected) 
- **Evaluates** performance with accuracy, precision/recall, F1, ROC AUC, and confusion matrices  
- **Deploys** feature-importance and calibration analyses to guide procurement actions

****

## Jupyter Notebooks
1. Cleaning:
   
   Open Notebooks/Cleaning.ipynb

   Run all cells to ingest, clean, and export cleaned_procurement_data.csv

2. Exploratory Data Analysis (EDA):
   
   Open Notebooks/EDA.ipynb

   Produce trend charts, histograms, correlation heatmaps, and vendor comparisons

3. Modeling:
   
   Open Notebooks/Modeling.ipynb

   Train, tune, and evaluate Logistic Regression and Random Forest models
   
   Generate performance reports, ROC/AUC, calibration curves, and feature importance

****
## Results
Best Model: Random Forest (AUC 0.741)

Key Predictors: defect_rate, defective_units, price_diff

Calibration: Brier score 0.134; slight overconfidence noted

The confusion matrix below illustrates the classification performance on the test dataset. All non-compliant orders (Class 0) were misclassified, indicating a need for advanced class imbalance handling in future iterations.

![Confusion Matrix](https://github.com/Bdowdle4/Dowdle_Analytics_Capstone/blob/main/Visualizations/RFCM.png)

****
## Future Work
* Apply resampling techniques like SMOTE (Synthetic Minority Oversampling) for oversampling class 0.

* Use class weighting in both logistic regression and random forest (class_weight='balanced').

* Lower the probability threshold from 0.5 → 0.4 to improve recall/precision on class 0.

* Implement custom loss functions to penalize the model more heavily for missing the minority class.

****

## Instructions On How To Set Up Your Virtual Environment and Run Your Notebook Locally
### Virtual Enviornment Set Up (Windows Users)
**Task 1. Create .venv** Run the following command from the project root directory. Use PowerShell (not cmd):

```shell
py -m venv .venv
```

**Accept VS Code Suggestions** If VS Code asks: We noticed a new environment has been created. 
Do you want to select it for the workspace folder? Click Yes. 

**Task 2. Activate** Run the following command from the project root directory. Use Powershell:

```powershell
.venv\Scripts\activate
```

### Run Jupyter Notebook Locally
**Before Starting** Ensure the .venv is activated. If it is already active, you don't need to reactivate it.

**Install the Jupyter Extension for VS Code** Open the Extensions view in VS Code by pressing Ctrl+Shift+X (Windows). Search for "Jupyter" and install the official extension.

**Open the Notebook in VS Code** Open the notebook in VS Code. The file will have a .ipynb extension.

**Task 1. Select Notebook Kernel** Open the project notebook in VS Code. The file will have a .ipynb extension.
- If prompted, select a Python interpreter that corresponds to your .venv.  
- If not prompted, click the kernel selector in the top-right corner of the notebook editor and choose the interpreter associated with your Python Environment / .venv.
- Or:
   - From VS Code Menu, select View / Command Palette... (CTRL SHIFT P)
   - Type: Python: Select Interpreter 
   - Choose your .venv from the list

**Task 2. Start and Run a Jupyter Notebook** Open the project notebook in VS Code. The file will have a .ipynb extension.

1. Execute cells:  
   - Click on a cell and press Shift+Enter to execute it and move to the next cell.  
   - Alternatively, use Ctrl+Enter to execute the current cell without moving.

2. Save your notebook periodically to avoid losing progress. Or make sure the File / Autosave option is on.

**ALWAYS: Fully Execute Notebooks before add-commit-push** Keep your notebooks organized and execute them fully before running git add-commit-push to GitHub.

****

## Repository Checklist

Verify your repository contains:

- [x] Useful .gitignore (that keeps .venv out of GitHub)
- [x] Professional Jupyter Notebooks with with proper names, numbered sections, and reflections 
- [x] Useful README.md
- [x] Useful requirements.txt
- [x] Dataset, stored in a data folder
- [ ] Peer Review (peer_review.md)

****

## Contributing
Thank you for exploring this capstone project! Feedback and questions are welcome.
1. Fork this repository

2. Create a feature branch: git checkout -b feature/my-feature

3. Commit your changes: git commit -m "Add my feature"

4. Push to your branch: git push origin feature/my-feature

5. Open a Pull Request—describe your changes & link relevant issues