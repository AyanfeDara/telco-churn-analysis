# Build guide: telecom churn analysis (Python)

**Business question:** which customers are most likely to leave, and if the company can only contact some of them with a retention offer, which ones should it contact?

**Result:** a Jupyter notebook with the analysis and model, three charts, and a README with findings and a recommendation. Time: 3 to 4 sessions.

---

## 1. Get the data (5 minutes)

1. Open <https://www.kaggle.com/datasets/blastchar/telco-customer-churn> (sign in) and click **Download**.
2. Unzip it and put `WA_Fn-UseC_-Telco-Customer-Churn.csv` in this project's `data` folder. Keep the file name exactly as it is; the notebook looks for it.

## 2. Open the notebook (5 minutes)

1. Open **Anaconda Navigator** and click **Launch** on **Jupyter Notebook** (or **JupyterLab**). A browser tab opens showing your folders.
2. Click through to `Project Portfolio\telco-churn-analysis` (or wherever you saved it) and open `churn_analysis.ipynb`.
3. Run each cell in order with **Shift + Enter**. Read each output before moving on.

If a cell shows `ModuleNotFoundError`, open **Anaconda Prompt** and run `pip install scikit-learn scipy`, then restart the notebook (**Kernel > Restart**).

## 3. Check your numbers

Your output should match these. If something differs, stop and find out why before continuing.

| Section | Check | Expected |
| --- | --- | --- |
| 2. Load | Rows, columns | 7,043, 21 |
| 2. Clean | Blank `TotalCharges` | 11, all with tenure 0 |
| 3. Churn | Churn rate | 26.5% |
| 3. Churn | Monthly revenue of leavers | $139,131 of $456,117 (30.5%) |
| 4. Groups | Churn rate: month-to-month / one year / two year | 42.7% / 11.3% / 2.8% |
| 4. Groups | Churn rate: first 12 months | 47.4% |
| 4. Groups | Churn rate: fibre optic / electronic check | 41.9% / 45.3% |
| 4. Tests | Gender | Not significant (p = 0.49) |
| 5. Model | ROC AUC, logistic regression / random forest | 0.847 / 0.845 |
| 6. Targeting | Top 20% of test customers | 235 of 467 leavers (50%), 55% of their lost revenue |

## 4. Write your readings (the important part)

Each section ends with a **Your reading** cell. Double-click it, replace the placeholder with two or three sentences **in your own words**, and press **Shift + Enter**. These sentences become your README findings and your interview answers.

Points to think about:

- **Section 4:** a group that churns more is not proof of cause. Month-to-month customers can leave easily *because* they have no contract; that is part of what the contract type measures.
- **Section 5:** why ROC AUC instead of accuracy? A model that says "nobody leaves" is already 73% accurate.
- **Section 5:** the two models score almost the same. Which would you present to a manager, and why?
- **Section 6:** what does "contacting 20% reaches 50% of leavers" mean in money and effort, compared with picking customers at random?

## 5. Write the README (1 session)

Fill in `README.md`: title with the main result, three or four findings with numbers and charts, the recommendation, method and limitations. Use only numbers that appear in your notebook output.

## 6. Publish on GitHub (30 minutes)

1. Create a new public repository `telco-churn-analysis` (README off).
2. Upload `churn_analysis.ipynb`, `README.md`, `GUIDE.md`, `requirements.txt` and the `charts` folder. Leave out the `data` folder: anyone can download the file from Kaggle.
3. Add `.gitignore` by hand (**Add file > Create new file**), copying the contents of the `.gitignore` in this folder.
4. Topics: `python`, `machine-learning`, `scikit-learn`, `churn-prediction`, `data-analysis`, `jupyter-notebook`.

**Save the notebook with its outputs** (File > Save) before uploading. GitHub then shows the tables and charts without anyone needing to run it.
