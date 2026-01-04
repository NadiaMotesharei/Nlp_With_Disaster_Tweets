# GitHub Copilot instructions for this repository ✅

Purpose
- Help an AI coding agent become productive quickly: explain the project layout, how to run the work, and repository-specific conventions.

Quick summary
- This is an exploratory NLP project implemented as a single Jupyter notebook: `Nlp_DisasterTweets.ipynb`.
- No CI, tests, or requirements file were found. Dependencies are inferred from the notebook imports.

How to run locally 🔧
1. Create and activate a virtual env (Windows example):
   - `python -m venv .venv` and `\.venv\Scripts\activate`
2. Install minimal dependencies inferred from the notebook:
   - `pip install numpy pandas scikit-learn tensorflow`
3. Open `Nlp_DisasterTweets.ipynb` in VS Code or Jupyter and run the cells.
4. The notebook prints `tf.__version__` in the first code cell—use this to validate the environment.

Key files and patterns 📁
- `Nlp_DisasterTweets.ipynb` — **single source of truth** for data loading, preprocessing, modeling, and evaluation. Prefer modifying the notebook for exploratory work.
- Example import block from the notebook (use for dependency discovery):

```python
import numpy as np
import pandas as pd
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras.layers import TextVectorization
from sklearn.model_selection import StratifiedKFold
from sklearn.metrics import accuracy_score
```

Repo conventions & discoverable facts 🔎
- No `requirements.txt`, `environment.yml`, or `pyproject.toml` present — add one when adding durable scripts.
- No tests or CI configuration detected — assume manual testing runs via the notebook.
- No dataset files present — dataset likely expected to be acquired externally (e.g., Kaggle). Do not add large dataset files to the repo; instead add a `data/` entry to `.gitignore` and document download steps in `README.md`.

When you edit
- For exploratory changes, update the notebook and keep code cells small and well-documented.
- If you convert notebook code into modules (e.g., `src/`), add a `requirements.txt`, a small unit test (pytest), and update README with run instructions.
- Keep notebook outputs minimal in commits (clear large outputs when possible) or use `nbstripout`/similar before committing.

What to avoid / assumptions ⚠️
- No CI or test harness; do not assume automated checks exist.
- Don't change or remove the `Nlp_DisasterTweets.ipynb` entry point without adding a clear replacement and run instructions.

Questions for maintainers
- Where do you expect the dataset to come from? (Kaggle link/credentials?)
- Do you want an executable script (e.g., `train.py`) alongside the notebook for reproducibility?

If any instruction is unclear or you want more details (e.g., preferred dependency versions or target Python), tell me and I will iterate. ✨
