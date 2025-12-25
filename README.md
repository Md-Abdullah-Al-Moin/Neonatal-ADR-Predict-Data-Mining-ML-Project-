# Neonatal ADR Prediction System

A Flask-based machine learning app that predicts adverse drug reaction (ADR) type and outcome severity for neonatal patients. The system uses CatBoost classifiers for inference and SHAP for model explainability.

## Highlights

- Dual classifiers: reaction category and outcome severity
- Web UI for real-time predictions
- SHAP plots to explain feature contributions
- Label encoding for categorical features
- Lightweight visualization with matplotlib

## Tech Stack

- Flask, pandas, scikit-learn
- CatBoost (classification)
- SHAP (explainability)
- matplotlib, joblib

## Repository Layout

- `app.py` — Flask server and prediction routes
- `train_model.py` — Training pipeline for reaction and outcome models
- `utils.py` — Preprocessing, inference, and SHAP utilities
- `requirements.txt` — Python dependencies
- `templates/` — HTML views (`index.html`, `result.html`)
- `static/` — Generated plots (e.g., SHAP feature importance)
- `models/` — Saved model artifacts (generated)
- `data/` — Dataset (restricted; not included)

## Getting Started

### Prerequisites

- Python 3.8 or newer
- `pip`

### Install Dependencies

```bash
pip install -r requirements.txt
```

## Run the Web App

```bash
python app.py
```

Open `http://localhost:5000` in your browser.

### Typical Workflow

1. Select medication (active ingredient)
2. Choose indication (reason for use)
3. Enter patient details: sex, age, weight
4. Click “Predict”
5. View predicted labels, probabilities, and a SHAP feature contribution plot

### Application Screenshots

| Input Interface | Results Page |
|-----------------|-------------|
| ![Input Form](https://drive.google.com/uc?id=1yhqdjHCRrBMndkI7zVQz758FN8SShxfY) | ![Results Page](https://drive.google.com/uc?id=1SUwoAXsESxb8aAf33lnNczZ2GK0ds6WG)

## Train the Models

```bash
python train_model.py
```

This trains two CatBoost classifiers (reaction type and outcome severity) and saves artifacts to `models/`. Training requires access to the clinical dataset.

## Data Access

The training dataset contains sensitive neonatal clinical information and is not publicly distributed. To request access for research or educational purposes, contact:

- Md. Abdullah Al Moin — midul7714@gmail.com
- Md. Zehadul Islam — gg.solve.zehadul999@gmail.com

Please include your name, institution, and research purpose. Requests are reviewed case-by-case.

## Explainability

Predictions are accompanied by SHAP-based visualizations that highlight which features influenced the model’s output. Plots are saved under `static/` and shown on the results page.

## Notes & Compliance

- This project uses protected clinical data. Handle all data in accordance with applicable regulations (e.g., HIPAA, GDPR) and institutional policies.
- The system is intended for research and decision support only. It is not a replacement for clinical judgment.

## Troubleshooting

- Missing model files: ensure `models/` contains the required artifacts or run `train_model.py` with approved data.
- SHAP plot issues: verify dependencies match `requirements.txt` and that `static/` is writable.
- Encoding errors: confirm categorical inputs match expected label encoders.

## License & Disclaimer

Developed for educational and research use. Not intended for clinical decision-making without proper validation, oversight, and regulatory approval.

---

Last updated: December 2025 · Status: Active Development
