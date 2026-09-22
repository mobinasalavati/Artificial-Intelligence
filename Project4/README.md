# Project 4 – Music Genre Classification with Scikit-Learn

Computer Assignment 4 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

## Problem

Predict a track's music genre from a Spotify-collected dataset (`dataset.csv`) of audio features —
popularity, duration, energy, danceability, acousticness, etc. — using classic Scikit-Learn models,
across four phases: exploratory data analysis, preprocessing, individual model tuning, and ensemble
learning.

## What's implemented

### Phase 0 — EDA & Visualization

- Dataset overview with `describe()` / `info()`.
- Percentage of missing values per feature.
- Distribution plots for numeric features (`popularity`, `acousticness`, `danceability`,
  `duration_ms`, `energy`, `instrumentalness`, `liveness`, `loudness`, `speechiness`, `tempo`,
  `valence`) and categorical features (`key`, `mode`) against the target genre.

### Phase 1 — Preprocessing

- Missing-value handling: numeric columns imputed with the median; the high-cardinality
  `artist_name` column (5,090 unique values) and `track_name` dropped rather than encoded.
- Feature scaling via **standardization** (chosen after observing the roughly normal distributions
  from Phase 0).
- Categorical encoding via **one-hot encoding** for `key` and `mode`.
- **Information gain** (`mutual_info_classif`) computed and plotted per feature to guide feature
  selection.

### Phase 2 — Model Training, Evaluation & Hyperparameter Tuning

- Stratified train/test split (`train_test_split` with `stratify`) to preserve genre proportions.
- **K-Nearest Neighbors**: accuracy vs. `n_neighbors` plotted for train and test sets to visualize
  overfitting; best `k` selected (35).
- **Decision Tree**: accuracy vs. `max_depth` / `min_samples_leaf` tuned the same way.
- Accuracy, Precision, Recall and F1-score reported for both models on train and test data, plus a
  discussion of how each preprocessing choice affected the final metrics.

### Phase 3 — Ensemble Methods

- **Random Forest** implemented with Scikit-Learn, tuning `n_estimators`, `max_depth`, and
  `min_samples_leaf`.
- Final accuracy/precision/recall/F1 reported, along with a **confusion matrix** for the tuned model.

## Tech stack

- Python, Jupyter Notebook
- `scikit-learn` (KNN, Decision Tree, Random Forest, `train_test_split`, `mutual_info_classif`,
  metrics), `pandas`, `matplotlib`

## Files

- `AI_CA4.ipynb` — EDA, preprocessing, model tuning, and ensemble learning
- `dataset.csv` — Spotify track dataset with audio features and genre labels
- `accuracy.png`, `precision.png`, `recall.png`, `f1_score.png` — saved evaluation plots referenced
  in the notebook

## License

MIT
