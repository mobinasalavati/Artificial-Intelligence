# Project 0 – Bank Term Deposit: EDA & Simple Statistical Classification

Computer Assignment 0 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

## Overview

This project is an introduction to `pandas`, `numpy`, `matplotlib` and Jupyter Notebook through
exploratory data analysis (EDA) and a simple statistical classifier. The task is to explore a bank
marketing dataset, clean and preprocess it, visualize feature distributions, and predict the missing
values of the target column using a Gaussian (normal distribution) statistical model — all built with
vectorized pandas/numpy operations (no explicit Python loops), as required by the assignment.

## Dataset

`bank_term_deposit.csv` contains one row per bank customer, with the following fields:

- age, job, marital status, education
- average yearly account balance
- whether the customer has a housing loan / personal loan
- duration of the last contact call (seconds)
- number of contacts performed during this campaign
- number of days since the last contact from a previous campaign (`pdays`)
- outcome of the previous marketing campaign (`poutcome`)
- **target (`y`)**: whether the customer subscribed to a term deposit — missing for a subset of rows

## What the notebook does

1. Loads the CSV into a `pandas` DataFrame and inspects it with `head`, `tail`, `info`, `describe`.
2. Label-encodes categorical columns (e.g. `marital`: divorced/single/married → 0/1/2).
3. Detects missing (`NaN`) values per column and imputes them with the column mean (except the
   target column), discussing the trade-offs of mean imputation.
4. Splits off the rows whose target (`y`) is missing into a separate DataFrame for later prediction.
5. Answers exploratory questions with vectorized pandas calls, e.g.:
   - counts of customers with/without a housing loan, and with/without a term deposit
   - number of single customers over 35 whose previous campaign outcome was `success`
   - average yearly balance for customers with `secondary` education
6. Repeats one of the aggregations using an explicit Python loop and times both the vectorized and
   loop-based versions to compare performance.
7. Plots histograms of every numeric column to inspect their distributions.
8. Normalizes numeric features (subtracting the mean, dividing by the standard deviation).
9. For each candidate feature, computes the mean/std separately for the `yes` and `no` classes
   (age, duration, balance, campaign, pdays) and plots the two Gaussian probability density curves
   to pick the most discriminative feature for classification.
10. Uses the mean/std of the chosen feature to predict the class (subscribed / not subscribed) for
    the rows with a missing target, and saves the predictions (with their row index) to a CSV file.

## Tech stack

- Python, Jupyter Notebook
- pandas, numpy, matplotlib, scipy.stats

## Files

- `AI_CA0.ipynb` — main notebook with all analysis, code and plots
- `bank_term_deposit.csv` — input dataset

## License

MIT
