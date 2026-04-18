# Pneumonia Predictor DL

Pneumonia Predictor DL is a deep learning project for binary chest X-ray classification:
- NORMAL
- PNEUMONIA

The current public pipeline is implemented in `Predictor_model.ipynb`.

## Project Snapshot

- Problem type: Medical image binary classification
- Framework: TensorFlow / Keras
- Input: Chest X-ray images
- Output: Probability of pneumonia
- Current status: Stable notebook pushed, transfer-learning notebook in progress

## Features

- Image preprocessing
- Data augmentation
- CNN-based binary classification
- Model evaluation with confusion matrix and classification report
- No-retraining mode for loading an already trained model

## Folder Structure

- `Predictor_model.ipynb` - main notebook used in this repository
- `Dataset/` - local dataset folder (ignored in git)
  - train/NORMAL
  - train/PNEUMONIA
  - val/NORMAL
  - val/PNEUMONIA
  - test/NORMAL
  - test/PNEUMONIA
- `requirements.txt`
- `.gitignore`

## Dataset

Kaggle source:
- `paultimothymooney/chest-xray-pneumonia`

Expected structure:

```text
Dataset/
  train/
    NORMAL/
    PNEUMONIA/
  val/
    NORMAL/
    PNEUMONIA/
  test/
    NORMAL/
    PNEUMONIA/
```

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

## Run

1. Open `Predictor_model.ipynb`.
2. Run all cells top-to-bottom.
3. Verify dataset path before training/evaluation cells.

## Kaggle Token Setup

1. Generate an API token from your Kaggle account.
2. Save `kaggle.json` on your local machine.
3. Place it at this path (recommended):
  - `%USERPROFILE%\.kaggle\kaggle.json`
4. Never commit `kaggle.json` to git.

## Run Without Retraining

If training is already complete, skip retraining.

1. Keep one trained model file in the project root:
  - `pneumonia_predictor_model.keras`
  - `pneumonia_predictor_model.h5`
2. Set `TRAIN_FROM_SCRATCH = False` in the notebook.
3. Run the evaluation and prediction cells directly.

## Current Status

- `Predictor_model.ipynb` is stable and currently published.
- `model.ipynb` is work in progress and will be updated later.

## Roadmap

- Complete the pretrained/transfer learning version
- Add better metrics tracking
- Add a single-image prediction script
