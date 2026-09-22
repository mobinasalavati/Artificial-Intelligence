# Project 3 – Naive Bayes Text Classification (Persian News Articles)

Computer Assignment 3 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

## Problem

Classify Persian articles from Digikala Mag into one of four categories — **Science & Technology**,
**Art & Cinema**, **Video Games**, and **Health & Beauty** — based only on each article's text, using
a Naive Bayes classifier built from scratch (no `sklearn` for the model or metrics).

## What's implemented

### Phase 1 — Preprocessing (`Preprocessor` class)

- Text normalization with the **Parsivar** library: lowercasing, removing digits/punctuation/extra
  whitespace, and half-space (`‌` → `#`) handling.
- Tokenization into words.
- **Stemming** (reducing words to their root, e.g. کتاب‌ها → کتاب).
- **Stop-word removal** using the bundled Persian stop-word list (`persian`).

### Phase 2 — Naive Bayes classifier (`Classifier` class)

- Bag-of-words model: each word's frequency per class is used to estimate
  `P(word | class)`, combined with the class prior to get the posterior `P(class | text)`.
- **Additive (Laplace) smoothing** to handle words unseen in a given class (or never seen at all)
  during training, avoiding zero probabilities.
- Bigram analysis (discussed in the report) as an extension beyond unigram bag-of-words to capture
  local word context.
- Bar charts of the top frequent words per category, and histograms confirming the train/test class
  balance.

### Phase 3 — Evaluation

- Accuracy, Precision, Recall and F1-score implemented manually (verified against
  `sklearn.metrics.classification_report`), reported per class and aggregated with **macro**,
  **micro**, and **weighted** averaging.
- Side-by-side comparison of results with and without additive smoothing, and with/without
  preprocessing, to quantify each step's contribution.
- Misclassified test examples collected and analyzed (`store_wrongly_detected`).

## Tech stack

- Python, Jupyter Notebook
- `parsivar` (Persian text normalization, tokenization, stemming), `pandas`, `matplotlib`,
  `prettytable`

## Files

- `AI_CA3.ipynb` — preprocessing, Naive Bayes implementation, evaluation and analysis
- `naive.png` — Bayes' theorem reference image used in the notebook
- `persian` — Persian stop-word list used during preprocessing

Note: the `train.csv` / `test.csv` dataset referenced by the notebook (expected under `data/`) is not
included in this repository.

## License

MIT
