# Python Learning Project

A structured 14-week Python learning journey from intermediate to advanced.

## Why `uv` for This Project?

✅ **Yes, `uv` is perfect for this learning project!** Here's why:

- **Fast Python version management** - Get latest Python quickly
- **Isolated environment** - Keep learning dependencies separate
- **Easy Jupyter setup** - Manage notebook kernels cleanly
- **Simple script running** - `uv run python script.py` (no activation needed)
- **Fast package installs** - Much faster than pip

## Setup

### 1. Install Dependencies

```bash
uv sync
```

This creates a `.venv` virtual environment and installs:
- Jupyter (notebooks)
- IPython kernel (for notebook execution)
- IPython (enhanced REPL)

### 2. Register Jupyter Kernel (Already Done!)

The kernel is already registered. If you need to re-register:

```bash
uv run python -m ipykernel install --user --name python-learning --display-name "Python Learning"
```

### 3. Start Jupyter

```bash
# Classic Notebook
uv run jupyter notebook

# Or JupyterLab (recommended)
uv run jupyter lab
```

### 4. Select Kernel in Notebooks

When you open/create a `.ipynb` file:
1. Click the kernel name in the top right
2. Select **"Python Learning"**
3. Now your notebook uses the `uv`-managed Python environment!

## Daily Usage

### Running Python Scripts

```bash
# Option 1: Using uv run (no activation needed)
uv run python week-1/script.py

# Option 2: Activate environment first
source .venv/bin/activate
python week-1/script.py
```

### Adding Packages for Exercises

```bash
# Add a package (automatically updates pyproject.toml)
uv add numpy pandas matplotlib

# Install all dependencies
uv sync
```

### Checking Python Version

```bash
uv run python --version
```

## Project Structure

```
python-learning/
├── week-1/          # Functions & Closures
│   ├── t_1_functions.ipynb
│   └── exercises.py
├── week-2/          # Decorators
├── week-3/          # Iterators & Generators
├── ...
└── week-14/         # Design Patterns
```

Each week folder contains:
- `.ipynb` files for interactive learning
- `.py` files for scripts/exercises

## Tips

- **Always use the "Python Learning" kernel** in notebooks to ensure consistency
- Use `uv add <package>` when you need new libraries for exercises
- The `.venv` folder is gitignored - each person manages their own environment
- `uv sync` ensures everyone has the same dependencies

