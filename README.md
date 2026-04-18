# Pneumonia Predictor DL

![Python](https://img.shields.io/badge/Python-3.x-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Notebook](https://img.shields.io/badge/Notebook-Jupyter-informational)
![Status](https://img.shields.io/badge/Status-Active-success)

Deep learning project to classify chest X-ray images into two classes:
- NORMAL
- PNEUMONIA

## Highlights

- End-to-end image classification pipeline in a single notebook
- Data preprocessing, augmentation, training, and evaluation
- No-retraining mode supported for already trained model files
- Ready-to-share GitHub structure with safe ignore rules

## Project Structure

- `Predictor_model.ipynb`: main notebook for this public version
- `Dataset/`: local dataset folder (ignored in git)
  - `train/NORMAL`, `train/PNEUMONIA`
  - `val/NORMAL`, `val/PNEUMONIA`
  - `test/NORMAL`, `test/PNEUMONIA`
- `requirements.txt`: required Python packages
- `.gitignore`: excludes dataset, secrets, envs, and model artifacts
- `kaggle.json.example`: safe sample file

## Dataset

Kaggle source:
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

## Quick Start

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

Open `Predictor_model.ipynb` and run cells top-to-bottom.

## Kaggle Setup (Safe)

1. Generate API token from Kaggle account settings.
2. Save `kaggle.json` locally.
3. Place it at `%USERPROFILE%\.kaggle\kaggle.json` (recommended).
4. Never commit `kaggle.json`.

## Run Without Retraining

If your training is already complete, skip retraining.

1. Keep one trained model file in project root:
   - `pneumonia_predictor_model.keras` (preferred)
   - `pneumonia_predictor_model.h5`
2. In notebook, keep `TRAIN_FROM_SCRATCH = False`.
3. Run evaluation and prediction cells only.

Model files are ignored by git to keep the repository lightweight.

## Results

The notebook includes:
- Test-set evaluation
- Confusion matrix
- Classification report
- Accuracy and loss curves (available when training runs in-notebook)

You can add your best metrics here after final run:
- Test Accuracy: `TODO`
- Precision: `TODO`
- Recall: `TODO`
- F1 Score: `TODO`

## Current Scope

- Public version currently focuses on `Predictor_model.ipynb`
- `model.ipynb` is still experimental and intentionally excluded for now

## Future Improvements

- Finalize transfer-learning notebook
- Add model checkpointing and best-model tracking
- Add single-image inference notebook/script
- Add Grad-CAM style explainability visualization
