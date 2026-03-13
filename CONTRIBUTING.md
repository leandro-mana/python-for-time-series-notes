# Contributing to Python for Time Series Notes

This repository follows a professional, chapter-based workflow consistent with the
[python-for-data-science-notes](https://github.com/leandro-mana/python-for-data-science-notes),
[data-algorithms-with-pyspark](https://github.com/leandro-mana/data-algorithms-with-pyspark),
[mysql-notes](https://github.com/leandro-mana/mysql-notes), and
[postgres-notes](https://github.com/leandro-mana/postgres-notes) repository patterns.

## Workflow

### 1. Branch per Chapter

Create a feature branch for each chapter:

```bash
git checkout -b feature/chapter-01
git checkout -b feature/chapter-02
```

### 2. Chapter Structure

Each chapter directory should contain:

```bash
src/chapter_XX/
├── __init__.py            # Module docstring describing the chapter
├── README.md              # Chapter overview, notebook table, key concepts
├── 01_topic_name.ipynb    # Jupyter notebooks (primary content)
├── 02_another_topic.ipynb
└── data/                  # Sample data files if needed (prefer src/data/ for shared datasets)
```

### 3. Jupyter Notebooks

Notebooks are the primary learning material. When creating them:

1. Keep each notebook focused on one topic
2. Interleave markdown explanations with executable code cells
3. Number notebooks sequentially: `01_topic_name.ipynb`, `02_another_topic.ipynb`
4. Include output for key demonstrations
5. Use type hints in Python code where appropriate
6. Each notebook should start with the necessary imports
7. Use modern APIs only (statsmodels >= 0.14, pandas >= 2.2, prophet, Keras 3)

### 4. Chapter READMEs

Each chapter README should include:

- **Overview**: Brief chapter summary
- **Notebooks table**: All notebooks with topics covered
- **Key Concepts**: Main ideas covered in the chapter
- **References**: Credit foundational sources (FPP3, Portilla) where applicable

### 5. Code Quality

Before committing, run all checks:

```bash
# Single command to check everything
make check

# Or individual checks
make lint              # Ruff linter
make format            # Code formatting
make type-check        # mypy type checking
```

### 6. Commit Messages

Write clear commit messages:

- `feat(ch01): Add getting started with time series notebooks`
- `feat(ch08): Add ARIMA models notebooks`
- `docs(ch04): Update decomposition chapter README`
- `fix(ch07): Fix exponential smoothing API for statsmodels 0.14`

### 7. Pull Request

When ready, open a PR with:

- Clear title: `Add Chapter 07 - Exponential Smoothing`
- Description of notebooks included and concepts covered

## Code Style

Enforced by `make format` (ruff):

- Line length: 100 characters
- 4 spaces for indentation
- f-strings for formatting
- snake_case for functions/variables
- PascalCase for classes
- UPPER_CASE for constants
