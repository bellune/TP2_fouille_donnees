## Purpose
Provide focused, repo-specific instructions for AI coding agents working on this project.

## Repo Overview (big picture)
- Single analysis task implemented as a Jupyter notebook: `Q5_Q6.ipynb`.
- Primary data file: `winequality.csv` (local, small CSV used by the notebook).
- README.md is a short assignment description; there is no package manifest or environment file.

## What an agent should know first
- The codebase is notebook-centric. Most logic lives inside `Q5_Q6.ipynb` rather than modular Python packages.
- Data flow: notebook loads `winequality.csv`, performs preprocessing/analysis (cells), and produces figures/tables. Search the notebook for `read_csv` to find the exact load cell.

## Typical developer workflows
- Open and run `Q5_Q6.ipynb` in VS Code/Jupyter to reproduce results. Prefer running the notebook interactively rather than executing isolated cells out of context.
- If the environment is missing, create a virtualenv and install common data libraries:

```
python3 -m venv .venv
source .venv/bin/activate
pip install pandas numpy matplotlib seaborn scikit-learn jupyterlab
```

- If you add long-running scripts or tests, extract reusable functions into a small module (e.g., `src/` or `notebook_helpers.py`) and import them from the notebook.

## Project-specific conventions and patterns
- Keep the dataset path as a relative path: use `pd.read_csv("winequality.csv")` so kernels opened from repository root can run without edits.
- Prefer adding small helper modules for heavy computation rather than embedding large blocks in notebook cells; this keeps the notebook readable and supports unit testing.
- When editing the notebook for logic changes, leave descriptive markdown cells explaining the purpose of each analysis section (Q5, Q6).

## Useful quick searches (examples)
- To find data loading: search for `read_csv` or `winequality.csv` in the repo.
- To find model or metric calculations: search for `sklearn`, `train_test_split`, `fit(`, or `predict(` in the notebook cells.

## Integration points & external dependencies
- The only external artifact in the repo is the local CSV `winequality.csv`. There are no remote services or external APIs configured.
- Expect standard PyData dependencies (pandas, numpy, scikit-learn, matplotlib/seaborn). If imports fail, prompt the user before installing packages.

## Editing, committing, and PR notes
- Notebooks can be noisy in diffs. When making changes intended for review, clear large output cells before committing or use `nbstripout` / `jupytext` if the user requests.
- Small code additions should preferably be committed as separate `.py` helper files and imported by the notebook to keep diffs minimal.

## Questions the agent should ask if ambiguous
- Do you want me to run the notebook and produce updated outputs/figures?
- Should I create a `requirements.txt` or `environment.yml` for reproducibility?

## Where to look in this repo
- Primary analysis: `Q5_Q6.ipynb`
- Dataset: `winequality.csv`
- Assignment description: `README.md`

---
If this matches your intent I can refine wording, add example code snippets extracted from the notebook, or create a `requirements.txt` and small helper module for tests. What would you like next?
