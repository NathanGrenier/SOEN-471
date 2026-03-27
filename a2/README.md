# Assignment 2

Analyses and results can be found in the [following jupyter notebook](analysis.ipynb).

All assignment reference data can be found in the `/data` directory.

## Development Setup

We use **[uv](https://docs.astral.sh/uv/)** for dependency management.

### Install uv

**MacOS / Linux:** [Follow this Guide](https://docs.astral.sh/uv/getting-started/installation/#__tabbed_1_1)

**Windows:** [Follow this Guide](https://docs.astral.sh/uv/getting-started/installation/#__tabbed_1_2)

### Create & Sync Environment

To create your local virtual environment (`.venv`) and install all dependencies locked in `uv.lock`:

```bash
uv sync
```

### Enter the Environment

You can activate the environment in your terminal:

**MacOS / Linux:**
```bash
source .venv/bin/activate
```

**Windows:**
```powershell
.venv\Scripts\activate
```

### Managing Packages

**Add a package:**
```bash
uv add <package_name>
```

**Remove a package:**
```bash
uv remove <package_name>
```

### Formatting & Linting

We use **Ruff** for linting and formatting.

**Check for errors (Lint):**
```bash
uv run ruff check .
```

**Auto-format code:**
```bash
uv run ruff format .
```

> **VS Code Tip:** Install the `Ruff` extension. It will use the settings in `pyproject.toml` to format your code automatically on save.

## Project Data

`data/ecommerce_user_data.csv`:
```csv
UserID,ProductID,Rating,Timestamp,Category
U000,P0009,5,2024-09-08,Books
U000,P0020,1,2024-09-02,Home
U000,P0012,4,2024-10-18,Books
U000,P0013,1,2024-09-18,Clothing
U000,P0070,4,2024-09-16,Toys
U000,P0014,1,2024-09-15,Home
U000,P0048,5,2024-09-09,Toys
U000,P0079,4,2024-10-18,Electronics
U000,P0042,3,2024-09-07,Toys
U000,P0050,1,2024-10-14,Clothing
```

`data/product_details.csv`:
```csv
ProductID,ProductName,Category
P0000,Toys Item 0,Clothing
P0001,Clothing Item 1,Electronics
P0002,Books Item 2,Electronics
P0003,Clothing Item 3,Electronics
P0004,Clothing Item 4,Electronics
P0005,Home Item 5,Toys
P0006,Books Item 6,Books
P0007,Books Item 7,Books
P0008,Books Item 8,Electronics
P0009,Clothing Item 9,Books
P0010,Toys Item 10,Books
```