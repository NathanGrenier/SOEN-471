# E-Commerce Recommender System & Pattern Mining

## Overview
This project builds a data-driven product recommendation engine and conducts market basket analysis for an e-commerce platform. The goal is to increase customer lifetime value by serving personalized product suggestions and discovering natural product bundles.

The project is broken into two main analytical approaches:
1. **User-Based Collaborative Filtering:** A recommendation engine that generates personalized product lists by finding "similar" users based on their rating histories using Cosine Similarity. The model was evaluated using a rigorous 80/20 train-test split, tracking Cross-Validated Precision, Recall, and Catalog Coverage.
2. **Association Rule Mining:** Using the Apriori algorithm to discover frequent itemsets (products commonly bought together). By evaluating support, confidence, and high *lift* values, the system identifies strong dependencies between specific items for targeted cross-selling.

## Technical Highlights
* **Matrix Operations:** Built and optimized highly sparse user-item matrices for similarity computations.
* **Machine Learning Context:** Evaluated the cold-start and sparsity tradeoffs inherent to collaborative filtering.
* **Pattern Mining:** Processed large transaction datasets into association rules to extract interpretable, actionable business logic (e.g., discovering multi-item functional bundles).

## 📓 Notebook of Interest
* [**End-to-End Analysis & Modeling**](./analysis.ipynb): A comprehensive notebook containing the full pipeline:
  * **ETL & Preprocessing:** Building and optimizing highly sparse user-item matrices from raw transaction logs.
  * **Collaborative Filtering:** Implementing Cosine Similarity to generate user-based product recommendations, complete with a train/test split evaluation for precision, recall, and catalog coverage.
  * **Pattern Mining:** Applying the Apriori algorithm to extract association rules (support, confidence, lift) to discover high-value, multi-product bundles.

## Project Structure
- Core logic and evaluations are housed in `analysis.py` (and the corresponding `analysis.ipynb` notebook).
- Reference datasets are in `/data`.
- Outputs (Result tables `.csv` and visualization `.png` files) generate to the `results/` directory.

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

## Project Data Samples
User Interactions (`data/ecommerce_user_data.csv`):
```
UserID,ProductID,Rating,Timestamp,Category
U000,P0009,5,2024-09-08,Books
U000,P0020,1,2024-09-02,Home
U000,P0012,4,2024-10-18,Books
```

Product Catalog (`data/product_details.csv`):
```
ProductID,ProductName,Category
P0000,Toys Item 0,Clothing
P0001,Clothing Item 1,Electronics
P0002,Books Item 2,Electronics
```