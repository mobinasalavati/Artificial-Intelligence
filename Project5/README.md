# Project 5 – Feed-Forward Neural Networks

Computer Assignment 5 for the Artificial Intelligence course (University of Tehran, Spring 1401 / 2022).
Instructors: Dr. Fadaee & Dr. Yaghoobzadeh.

Two-phase project: building a feed-forward neural network from scratch with NumPy, then rebuilding
one with Keras/TensorFlow and exploring how training choices affect it.

## Phase 1 – Feed-forward NN from scratch (`Phase 1/AI-CA5.ipynb`)

Classifies Persian handwritten digits (0–9, ~102k grayscale images, resized to 25x25) using a
`FeedForwardNN` class implemented from scratch with NumPy (no deep learning framework) — layers,
activations, loss, and stochastic gradient descent all hand-written by completing a provided
skeleton notebook.

- **Preprocessing**: pixel value inspection, resizing to 25x25, per-class sample counts/plots,
  scaling pixels to `[0, 1]`.
- **Core classes**: `Dataloader`, `Layer`, `FeedForwardNN`, activation functions (`ReLU`, `Identical`,
  and others added later), and `CrossEntropy` loss (with softmax).
- **Baseline model**: trained with `lr=0.0001`, 15 epochs, batch size 32, ReLU activations
  (identity on the output layer), random weight initialization.
- **Experiments** (each isolating one change from the baseline):
  - weight initialization (why all-zero initial weights fail)
  - learning rate (baseline, 10x higher, 0.1x lower)
  - activation function: Sigmoid, Tanh, Leaky ReLU vs. ReLU (why Sigmoid/Tanh underperform here)
  - batch size: 16 and 256 vs. 32

## Phase 2 – Keras/TensorFlow feed-forward NN (`Phase 2/AI-CA5-p2.ipynb`)

Classifies handwritten English letters (A–Z) from the "A-Z Handwritten Alphabets" dataset
(`A_Z Handwritten Data.csv`, 28x28 grayscale images) using a Keras `Sequential` feed-forward network
(at least 2 hidden layers + softmax output; no convolutional/recurrent layers allowed).

- **Preprocessing**: load CSV with pandas, split into images/labels, per-class counts and sample
  plots, train/test split (10,000 test samples), pixel scaling (`/255`), one-hot label encoding.
- **Baseline model**: `make_feedforward_network` with 320/160 hidden units, SGD optimizer,
  `lr=0.01`, 10 epochs, batch size 32, ReLU hidden activations — compared against Tanh and Sigmoid.
- **Evaluation**: precision/recall/F1 (`classification_report`) plus loss/accuracy curves per epoch
  for every configuration below.
- **Optimizer effects**: SGD with momentum (0.5, 0.9, 0.98) vs. Adam.
- **Epoch count**: 10 vs. 20 epochs, and the overfitting trade-off.
- **Loss function**: MSE vs. categorical cross-entropy for classification.
- **Regularization**: L2 weight regularization (0.0001) and dropout, and their effect on
  overfitting.

## Tech stack

- **Phase 1**: Python, NumPy, OpenCV (image resizing), Matplotlib, pickle
- **Phase 2**: Python, TensorFlow/Keras, pandas, scikit-learn (`classification_report`), Matplotlib

## Files

- `Phase 1/AI-CA5.ipynb` — from-scratch NumPy feed-forward network and experiments
- `Phase 1/*.png` — activation function references and sample digit images used in the report
- `Phase 2/AI-CA5-p2.ipynb` — Keras feed-forward network, training, and experiments

Datasets (`Phase 1/dataset/*.pkl`, `Phase 2/dataset/A_Z Handwritten Data.csv`) are not included in
this repository.

## License

MIT
