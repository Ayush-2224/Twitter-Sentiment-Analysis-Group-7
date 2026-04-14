# Twitter Sentiment Analysis

A comparative study of multiple machine learning models for classifying tweet sentiment — Positive, Negative, and Neutral.

Models covered: Logistic Regression, Naive Bayes, SVM, Decision Tree, Random Forest, KNN, Perceptron, Gradient Boosting, AdaBoost, XGBoost, Neural Network, and BERT.

---

## What's Inside the ZIP

After extracting, your folder should look like this:

```
TwitterSentimentAnalysis/
│
├── TwitterSentimentAnalysis_group7.ipynb
├── twitter_training.csv
└── twitter_validation.csv
```

> ⚠️ All three files must stay in the **same folder**. Do not move or rename any of them.

---

## Prerequisites

- **Python 3.8 or higher** → [Download Python](https://www.python.org/downloads/)
- **Visual Studio Code** → [Download VS Code](https://code.visualstudio.com/)
- **Jupyter extension for VS Code** → install it from inside VS Code (step below)

---

## Setup & Installation

### 1. Extract the ZIP

Right-click the ZIP file and extract it to a folder of your choice.

### 2. Open the folder in VS Code

Go to **File → Open Folder** and select the extracted folder.

### 3. Install the Jupyter extension

- Click the **Extensions** icon in the left sidebar (or press `Ctrl+Shift+X`)
- Search for **Jupyter** (by Microsoft)
- Click **Install**

### 4. Open a terminal in VS Code

Go to **Terminal → New Terminal** (or press `` Ctrl+` ``).

### 5. (Recommended) Create a virtual environment

```bash
python -m venv venv
```

Activate it:

```bash
# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### 6. Install all required packages

```bash
pip install numpy pandas matplotlib seaborn scikit-learn nltk xgboost tensorflow ipykernel
```

> **Note on BERT:** The BERT section requires `transformers`, `datasets`, and `torch` — together about 1–2 GB. They are **not needed** to run the rest of the notebook. Only install if you want to run the BERT cells:
> ```bash
> pip install transformers datasets torch
> ```

---

## Running the Notebook

### 1. Open the notebook

In the VS Code Explorer (left sidebar), click on **`TwitterSentimentAnalysis_group7.ipynb`**. It will open as an interactive notebook directly in VS Code.

### 2. Select the Python kernel

When the notebook opens, click **Select Kernel** (top right corner) → choose the Python environment where you installed the packages (the `venv` you created, or your system Python).

### 3. Run the cells

- Run all cells at once: click **Run All** at the top of the notebook
- Run one cell at a time: click the **▶ play button** on the left of each cell, or press **Shift + Enter**

### 4. Skipping BERT (recommended for most users)

The BERT section is clearly marked with the heading `# BERT`. If you didn't install the heavy packages, simply **skip those cells** by not clicking run on them. All other models work completely independently.

---

## Notebook Sections

| Section | Description |
|---------|-------------|
| Data Loading | Loads `twitter_training.csv` |
| Data Cleaning | Removes nulls, duplicates, and `Irrelevant` rows |
| Preprocessing | Cleans text — lowercasing, removes URLs/mentions/hashtags, strips stopwords |
| Feature Extraction | TF-IDF vectorization |
| ML Models | Logistic Regression, Naive Bayes, SVM, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, XGBoost, KNN, Perceptron |
| Neural Network | Keras Dense network on TF-IDF features, uses `twitter_validation.csv` |
| BERT *(optional)* | Fine-tunes `bert-base-uncased` via Hugging Face Trainer |
| Final Comparison | Bar chart comparing all model accuracies |

---

## Results Summary

| Model | Accuracy |
|-------|----------|
| Neural Network | 91.1% |
| Random Forest | 89.6% |
| BERT | 89.1% |
| KNN | 88.3% |
| SVM | 77.4% |
| Logistic Regression | 75.4% |
| Perceptron | 72.8% |
| Naive Bayes | 71.3% |
| XGBoost | 65.8% |
| Gradient Boosting | 62.5% |
| AdaBoost | 51.5% |

---

## Troubleshooting

**`FileNotFoundError: twitter_training.csv`**
The CSV files must be in the exact same folder as the notebook. Do not rename them.

**Kernel not showing up**
Make sure you installed `ipykernel` in your environment: `pip install ipykernel`. Then reload VS Code and try selecting the kernel again.

**NLTK stopwords error**
The notebook downloads stopwords automatically. If it fails, run this once in the VS Code terminal:
```python
python -c "import nltk; nltk.download('stopwords')"
```

**TensorFlow import error**
Make sure you installed `tensorflow`: `pip install tensorflow`

**BERT cells fail or are very slow**
BERT requires a GPU for reasonable speed. On CPU it can take several hours. Skip the BERT section entirely if needed.
