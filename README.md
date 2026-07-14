# MNIST handwritten-digit classifier

A feed-forward neural network that classifies handwritten digits (0–9) from the classic
**MNIST** dataset, built with TensorFlow / Keras. Built end-to-end as a learning project:
data preprocessing → model design → training → evaluation.

## Result

> _Fill these in after running the notebook top-to-bottom:_
>
> - **Test accuracy:** **97.73%** (on the held-out test set)
> - A confusion matrix and a top-confusions breakdown are shown at the bottom of the notebook.

<!-- Tip: add a screenshot of the predictions grid or confusion matrix here, e.g.:
![Sample predictions](images/predictions.png) -->

## What it demonstrates

- **Data preprocessing** — normalizing pixel values (0–255 → 0–1) so inputs are on a
  comparable scale.
- **Proper data splitting** — separate **training**, **validation**, and **test** sets,
  where the model only ever learns on training data.
- **Model design** — a `Flatten → Dense(ReLU) → Dense(ReLU) → Dense(softmax)` network,
  with reasoning for each activation choice.
- **Optimizer & loss** — Adam + (sparse) categorical cross-entropy, the standard choices
  for multi-class classification.
- **Overfitting control** — early stopping on validation loss, plus training-vs-validation
  curves to diagnose the fit.
- **Evaluation** — final accuracy on unseen test data, a sample-predictions grid, and a
  confusion matrix.

## Project structure

```
mnist-neural-network/
├── mnist_classifier.ipynb   # the full notebook (run top-to-bottom)
├── requirements.txt         # dependencies
├── .gitignore
└── README.md
```

## How to run

1. (Recommended) create and activate a virtual environment.
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook mnist_classifier.ipynb
   ```
4. Run all cells top-to-bottom. MNIST downloads automatically via Keras on first run.

## What I learned

The full supervised-learning workflow — and the *why* behind each step: normalization for
stable training, a held-out validation set to detect overfitting, ReLU vs softmax
activations, cross-entropy for classification, Adam as the optimizer, and early stopping
to halt at the right time.

---

_Built while working through the deep-learning section of a data-science course._
