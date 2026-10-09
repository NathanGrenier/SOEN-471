# Customer Churn Prediction Engine

## Overview
This project focuses on predicting customer churn for a hypothetical streaming service, "StreamFlex". The goal is to identify users who are likely to cancel their subscriptions so the business can proactively intervene with retention strategies. 

The project encompasses two main phases:
1. **Exploratory Data Analysis (EDA):** Cleaning data, visualizing distributions, handling categorical encodings, and mapping correlations between user metrics (e.g., watch time, complaints) and churn rates.
2. **Predictive Modeling:** Building and tuning machine learning classifiers to predict churn. The final **Random Forest** model successfully achieved an F1-score of ~90%, heavily prioritizing *Recall* (95.6%) to ensure the vast majority of at-risk customers are successfully flagged.

## Technical Highlights
* **Algorithms Used:** Decision Tree, Random Forest.
* **Hyperparameter Tuning:** Utilized `GridSearchCV` with 5-fold cross-validation to find optimal tree depth, split criteria, and minimize overfitting.
* **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score, and Confusion Matrices.
* **Feature Importance Analysis:** Extracted model weights to provide actionable business insights, revealing that *Number of Complaints* and *Watch Time* are the heaviest drivers of customer churn.

## 📓 Notebooks of Interest
Click the notebooks below to view the executed code, visualizations, and step-by-step documentation:

* [**Data Preparation & EDA**](./data-preperation-and-EDA.ipynb): Demonstrates the extraction and transformation phases. Includes data quality checks, statistical summaries, correlation heatmaps, and visualizations to identify initial patterns in customer behavior.
* [**Churn Classifiers**](./churn-classifiers.ipynb): Showcases the machine learning pipeline. Walks through feature selection, model training (Decision Trees & Random Forests), hyperparameter tuning via `GridSearchCV`, and translates evaluation metrics (Precision/Recall) into actionable business strategy.

## Development Setup

We use **[uv](https://docs.astral.sh/uv/)** for dependency management.

### Install uv
* **MacOS / Linux:** [Follow this Guide](https://docs.astral.sh/uv/getting-started/installation/#__tabbed_1_1)
* **Windows:** [Follow this Guide](https://docs.astral.sh/uv/getting-started/installation/#__tabbed_1_2)

### Create & Sync Environment
To create your local virtual environment (`.venv`) and install all dependencies locked in `uv.lock`:
```bash
uv sync
```

### Enter the Environment
You can activate the environment in your terminal:

MacOS / Linux:
```bash
source .venv/bin/activate
```

Windows:
```powershell
.venv\Scripts\activate
```
`(Alternatively, you can run commands without activating by prefixing them with uv run, e.g., uv run jupyter lab)`

### Managing Packages
- Add a package: `uv add <package_name>`
- Remove a package: `uv remove <package_name>`
- Sync with team changes: `uv sync`

### Formatting & Linting
We use Ruff for linting and formatting.   

- Check for errors (Lint): `uv run ruff check .`
- Auto-format code: `uv run ruff format .`