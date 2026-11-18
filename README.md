# DSCI-522-Group4
DSCI-522-Group4 Milestone 1

## Setting up the environment

This project uses [uv](https://docs.astral.sh/uv/) to manage Python and its packages, and [Quarto](https://quarto.org/) to render the report.

1. Install uv by following the [uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).
2. Install Quarto by following the [Quarto installation guide](https://quarto.org/docs/get-started/).
3. Clone this repository and move into it:

   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group4.git
   cd DSCI-522-Group4
   ```

4. Create the environment. This installs the Python version in `.python-version` and the exact package versions in `uv.lock`:

   ```bash
   uv sync
   ```

## Adding a package

Add packages with `uv add <package>` (not by editing `pyproject.toml` by hand), and commit the updated `pyproject.toml` and `uv.lock` together in your pull request.
