# Heart disease data analytics — Group 7

**Problem statement:** To analyse how patient attributes are associated with heart disease using exploratory data analysis and statistical tests.

Data Analytics (CES2103), III semester B.Tech. CSE, Section I, Manipal Institute of Technology, MAHE.

## Team members

| Name | Roll number | Registration number |
|---|---:|---|
| Spandan Shetty | 21 | 251090050998 |
| Adarsh S P | 7 | 251090050196 |
| Siddharth Hari | 8 | 251090050231 |

## Dataset

The supplied `heart.csv` matches the 918-row, 12-column schema of Federico Soriano's [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) on Kaggle. It includes 11 attributes and the binary `HeartDisease` outcome. The file is retained unchanged. The outcome is a heart-disease label, not specifically a heart-attack outcome.

## Setup and run

Use Python 3.12. From the project folder:

```bash
python -m venv .venv
```

Activate the environment with `.venv\Scripts\Activate.ps1` in Windows PowerShell, or `source .venv/bin/activate` on macOS/Linux. Then:

```bash
python -m pip install -r requirements.txt
python -m notebook Heart_Disease_Analysis.ipynb
```

Keep `heart.csv` beside the notebook. Select **Kernel → Restart Kernel and Run All Cells**, then save. The submitted notebook already contains the outputs from a complete sequential run of all 14 code cells. Its only input is the relative path `heart.csv`.

## Findings

- 508 of 918 records (55.3%) have `HeartDisease = 1`.
- Exercise angina, chest-pain type and ST-slope are associated with the label in the three chi-square tests (p = 2.91e-50, 8.08e-58 and 5.17e-78).
- The disease-labelled group has lower mean MaxHR (127.66 vs 148.15) and higher mean age (55.90 vs 50.55). Two-sided Welch tests give p = 1.43e-36 and 6.35e-18.
- Zero cholesterol readings are treated as missing: 20/410 (4.9%) in label 0 and 152/508 (29.9%) in label 1. The separate missingness chi-square test gives p = 9.50e-22. These values are not filled using the outcome label. Measured cholesterol summaries cover only 746 records.
- One zero resting blood pressure is replaced with the nonzero median (130 mm Hg). All rows are retained.

The tests are exploratory comparisons selected after EDA. They assume independent records, do not establish causation or independent effects, and do not support medical diagnosis or population prevalence estimates.

## Files

- `Heart_Disease_Analysis.ipynb` — executable analysis with saved outputs.
- `heart.csv` — unchanged input data.
- `Team_07.pdf` — submission report.
- `Team_07.docx` — editable report; the three contribution fields are intentionally blank.
- `requirements.txt` — analysis imports and Jupyter Notebook, pinned to the verified environment.

Submit the notebook, CSV and PDF to the LMS. Complete the contribution fields in the editable report before submission if your instructor requires them, and export the updated PDF.
