# Heart Disease Prediction

This project predicts whether a patient is likely to have heart disease, based on routine clinical data. The goal was to build a model that is accurate but also simple enough to trust and explain, which matters a lot in healthcare.

Built with Python and scikit learn on the UCI Heart Disease dataset.

## About the project

Heart disease is one of the leading causes of death around the world, and spotting at risk patients early can genuinely help. I wanted to see how well a patient's chance of heart disease could be predicted from everyday clinical measurements, and to compare a few models to find which one works best.

## The data

The data comes from the UCI Heart Disease dataset, the Cleveland set, which you can read about here: https://archive.ics.uci.edu/dataset/45/heart+disease

It has 303 patient records and 14 clinical features, including age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, resting ECG results, maximum heart rate, and whether exercise brought on chest pain. The target is simply whether the patient has heart disease (1) or not (0).

A cleaned copy of the data is included in this repo as `heart-disease.csv`, so the notebook runs without any external downloads.

## What I did

1. Explored the data to understand the features, how they relate to each other, and how each one links to heart disease.
2. Prepared the data by handling a few missing values and checking data types.
3. Trained and compared three models:
   * Logistic Regression
   * Decision Tree (tuned with grid search)
   * K Nearest Neighbours (tuned with grid search)
4. Checked each model on accuracy, precision, recall, F1 score, and ROC AUC, using a test set the models had not seen.

## Results

| Model | Test accuracy | ROC AUC |
|---|---|---|
| Logistic Regression | about 85% | about 0.92 |
| Decision Tree (tuned) | about 81% | about 0.87 |
| K Nearest Neighbours (tuned) | about 67% | about 0.74 |

Logistic Regression came out on top. Its ROC AUC of about 0.92 means it does a good job of telling positive and negative cases apart, which is what you want when missing a real case is costly. I also looked at precision and recall for each model to understand the trade off between missing true cases and raising false alarms.

## What I took from it

* A simple model (Logistic Regression) beat the more complex ones here, which is a good reminder that a complicated model is not always a better one.
* Looking past accuracy to ROC AUC and precision and recall gives a much clearer picture of how useful a model really is.
* Chest pain type, maximum heart rate, and exercise brought on chest pain were some of the most useful features.

## Tools used

Python, pandas, NumPy, scikit learn, Matplotlib, Seaborn, Jupyter.

## How to run it

```bash
git clone https://github.com/sriram2708/heart-disease-prediction.git
cd heart-disease-prediction
pip install -r requirements.txt
jupyter notebook heart_disease.ipynb
```

## What's in here

* `heart_disease.ipynb` is the full analysis, from exploring the data through to comparing the models.
* `heart-disease.csv` is the cleaned dataset the notebook uses.
* `requirements.txt` lists the Python packages you need.
* `README.md` is this file.

Author: Sriram Venkatesh, Master of Data Science, RMIT University.
