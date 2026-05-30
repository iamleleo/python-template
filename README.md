# python-template

A template for Python projects using `uv` for fast dependency management.

## Getting Started

Ensure you have `uv` installed. If not, install it by following the instructions in the [official documentation](https://docs.astral.sh/uv/getting-started/installation/).

## Virtual Environment

To create a virtual environment, run:

```bash
uv venv
```

To activate the virtual environment on macOS/Linux:

```bash
source .venv/bin/activate
```

*(On Windows, use `.venv\Scripts\activate`)*

## Managing Packages

### Adding Packages

To add a new package (this will automatically update your `pyproject.toml` and `uv.lock`):

```bash
uv add <package_name>
```

**Example:** Adding common data science packages for your notebooks:

```bash
uv add pandas numpy matplotlib seaborn
```

To add a development dependency (like a testing framework or linter):

```bash
uv add --dev <package_name>
```

### Removing Packages

To remove a package:

```bash
uv remove <package_name>
```

## Default Configuration & Packages

Since this project is primarily for Jupyter Notebooks, we recommend having the following development packages installed:

- **JupyterLab** / **Notebook**: The interactive computing environment.
- **ipykernel**: Allows Jupyter to use the `uv` virtual environment.
- **Ruff**: An extremely fast Python linter and code formatter (it also supports formatting notebooks!).
- **Pytest**: A framework for running tests.
- **Mypy**: For static type checking.

You can add these default development tools by running:

```bash
uv add --dev jupyter ipykernel pandas numpy seaborn matplotlib scikit-learn
```

### Running Jupyter

Once installed, you can start JupyterLab by running:

```bash
uv run jupyter lab
```

*(Alternatively, to run the classic notebook: `uv run jupyter notebook`)*

Running it via `uv run` ensures that Jupyter automatically uses your `uv` virtual environment and has access to all your installed dependencies.