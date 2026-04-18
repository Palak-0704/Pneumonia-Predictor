# Pneumonia Predictor DL

Deep learning project to classify chest X-ray images into two classes:
- NORMAL
- PNEUMONIA


## Project Structure

- `Predictor_model.ipynb`: current end-to-end training notebook
- `Dataset/`: local dataset folder (ignored in Git)
  - `train/NORMAL`, `train/PNEUMONIA`
  - `val/NORMAL`, `val/PNEUMONIA`
  - `test/NORMAL`, `test/PNEUMONIA`
- `requirements.txt`: Python dependencies
- `.gitignore`: ignore rules for dataset, secrets, and environment files

## Dataset

This project uses the Kaggle dataset:
- `paultimothymooney/chest-xray-pneumonia`

Expected local structure:

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

## Environment Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

## Kaggle Setup (Safe)

1. Generate API token from Kaggle account settings.
2. Save `kaggle.json` locally.
3. Place it at:
   - `%USERPROFILE%\.kaggle\kaggle.json` (recommended)
4. Do not commit `kaggle.json` to GitHub.

## How to Run

1. Open `Predictor_model.ipynb`.
2. Run cells in order from top to bottom.
3. Confirm dataset path is detected correctly before training starts.

## Run Without Retraining

If you have already trained your model, you do not need to train again.

1. Keep your trained model file in project root with one of these names:
  - `pneumonia_predictor_model.keras` (preferred)
  - `pneumonia_predictor_model.h5`
2. In notebook training cell, keep `TRAIN_FROM_SCRATCH = False`.
3. Run remaining cells to evaluate and predict using the loaded model.

Note: model files are intentionally ignored in git to keep repository lightweight.

## GitHub Notes

- Ignored by default: `Dataset/`, `.venv/`, `kaggle.json`, model artifacts, zip files.
- Current public version focuses only on `Predictor_model.ipynb`.
- `model.ipynb` will be added/updated later after completion.

## Future Improvements

- Finalize pretrained transfer learning notebook
- Add evaluation metrics (precision, recall, F1, confusion matrix)
- Add model checkpointing and best model saving
- Add inference notebook/script for single-image prediction
