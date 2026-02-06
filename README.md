
# Principal Component Analysis (PCA) — Formative Assignment

## Overview

This project implements **Principal Component Analysis (PCA) from scratch** using NumPy to reduce the dimensionality of an African conflict dataset (ACLED: Armed Conflict Location & Event Data) while preserving as much variance as possible. PCA extracts relevant information by identifying principal components that explain the relationships between features in the data.

## Dataset

**ACLED Africa 1997–2020** (`Africa_1997-2020_Jan08.csv`)

- **Source**:https://www.kaggle.com/datasets/lumierebatalong/africa-conflict-19972020
- **Rows**: 65,536 conflict events across Africa
- **Columns**: 29 features (e.g., event type, actors, location, fatalities, coordinates)
- **Separator**: Semicolon (`;`)
- **Contains missing values**: Yes (e.g., `ASSOC_ACTOR_1`, `ASSOC_ACTOR_2`, `ACTOR2`)
- **Contains non-numeric columns**: Yes (e.g., `EVENT_TYPE`, `ACTOR1`, `COUNTRY`, `NOTES`)

## What This Notebook Does

| Step | Description |
|------|-------------|
| **Step 1** | Load data, handle missing values (mean imputation for numeric, 'Missing' label for categorical), encode non-numeric columns with LabelEncoder, and standardize using z = (x − μ) / σ |
| **Step 3** | Compute the covariance matrix to understand feature relationships |
| **Step 4** | Perform eigendecomposition to extract eigenvalues and eigenvectors |
| **Step 5** | Sort principal components by explained variance (descending) and visualize variance distribution |
| **Step 6** | Dynamically select components retaining ≥95% variance and project data |
| **Step 7** | Output the reduced dataset |
| **Step 8** | Visualize original feature space vs. PCA-transformed space with labeled axes and explanation |

## Installation & Setup

### Prerequisites

- Python 3.8+
- pip (Python package manager)

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/Principal-Component-Analysis.git
cd Principal-Component-Analysis
```

### 2. Install Dependencies

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
```

Or install from the requirements file:

```bash
pip install -r requirements.txt
```

### 3. Run the Notebook

**Option A — VS Code (Recommended)**
1. Open the folder in VS Code
2. Install the **Jupyter** extension (`ms-toolsai.jupyter`)
3. Open `PCA Formative 2.ipynb`
4. Select a Python kernel (top-right corner)
5. Click **Run All** or run cells individually with `Shift+Enter`

**Option B — Jupyter Notebook**
```bash
jupyter notebook "PCA Formative 2.ipynb"
```

**Option C — Google Colab**
1. Upload the notebook and CSV to Google Colab
2. Update the CSV path in the first code cell to `/content/Africa_1997-2020_Jan08.csv`
3. Run all cells

## Dependencies

| Package | Purpose |
|---------|---------|
| `numpy` | Matrix operations, eigendecomposition, standardization |
| `pandas` | Data loading and manipulation |
| `matplotlib` | Visualization (before/after PCA plots) |
| `scikit-learn` | LabelEncoder for categorical encoding |

## Key Results

- **Data Handling**: Missing values imputed, 29 columns (including non-numeric) processed
- **Explained Variance**: Eigenvalues sorted in descending order; components selected dynamically based on 95% cumulative variance threshold
- **Visualization**: Side-by-side comparison of original feature space vs. PCA-transformed space with properly labeled axes (PC1 & PC2 with variance percentages)

## Project Structure

```
Principal-Component-Analysis/
├── Africa_1997-2020_Jan08.csv    # ACLED conflict dataset
├── PCA Formative 2.ipynb         # Completed PCA notebook
└── README.md                     # This file
```

## Author
Jeremie Iyamurinze — ALU (African Leadership University)
