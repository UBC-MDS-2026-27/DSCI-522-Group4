# Predicting Summit Success in the Nepal Himalaya

**Authors:** Rohan Chakkadath, Laith Saeed, Evan Pai and Harshil Sharma

Data analysis project for DSCI 522 (Data Science Workflows),
as part of UBC's Master of Data Science program.


## Summary

This project asks whether information known before a Himalayan expedition sets off can predict whether a climber will reach the summit. We treat this as a binary classification problem and use supervised machine learning models. The data contain 59,904 member records from 8,420 expeditions in the Nepal Himalaya between 1990 and 2019.

Our final gradient boosting model reached a balanced accuracy of 0.71 on the test set. In cross-validation, logistic regression reached 0.68 (0.65 without the expedition oxygen indicator), and both models clearly outperformed a dummy baseline that always predicts the most frequent outcome (0.50).

One important limitation is that the expedition oxygen indicator may be partly recorded after the climb, which would make our results somewhat optimistic. When we removed it, logistic regression's balanced accuracy dropped from 0.68 to 0.65.

## Report

The rendered report is available
[here](https://ubc-mds-2026-27.github.io/DSCI-522-Group4/analysis/himalayan-summit-prediction.html).
Its source is [`analysis/himalayan-summit-prediction.qmd`](analysis/himalayan-summit-prediction.qmd).

## Usage

### Setting up the environment

This project uses [uv](https://docs.astral.sh/uv/) to manage Python and its
packages, and [Quarto](https://quarto.org/) to render the report.

1. Install uv by following the [uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).
2. Install Quarto by following the [Quarto installation guide](https://quarto.org/docs/get-started/).
3. Clone this repository and move into it:

   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group4.git
   cd DSCI-522-Group4
   ```

4. Create the environment. This installs the Python version in
   `.python-version` and the exact package versions in `uv.lock`:

   ```bash
   uv sync
   ```

### Running the analysis

From the root of the repository, run:

```bash
uv run quarto render analysis/himalayan-summit-prediction.qmd
```

This runs the whole analysis from scratch and takes a few minutes. It
downloads the data again from the TidyTuesday repository (so you need an
internet connection), overwrites the files in `data/raw/` and
`data/processed/`, and writes the report to
`analysis/himalayan-summit-prediction.html`.

### Adding a package

Add packages with `uv add <package>` (not by editing `pyproject.toml` by hand),
and commit the updated `pyproject.toml` and `uv.lock` together in your pull
request.

## Dependencies

- [uv](https://docs.astral.sh/uv/) (version 0.12 or higher)
- [Quarto](https://quarto.org/) (version 1.10 or higher)
- Python 3.12 and the packages listed in [`pyproject.toml`](pyproject.toml)
  (exact versions are locked in [`uv.lock`](uv.lock))

## AI use statement

Our team used Claude Code (Anthropic), running the Claude Opus 5.5 and Claude Sonnet 5.5 models, for troubleshooting, tutoring, drafting code and text, and proofreading and formatting. All AI-assisted work was reviewed by team members. Please see the [`AI_USAGE.md`](AI_USAGE.md) for a full breakdown of how AI aided in the preparation of this project. 

## License

The code in this repository is licensed under the MIT License. The report
(its text, figures and tables) is licensed under the
[Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License (CC BY-NC-ND 4.0)](https://creativecommons.org/licenses/by-nc-nd/4.0/).
See [`LICENSE.md`](LICENSE.md) for the full text of both licenses.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for how to report a problem or
suggest a change, and [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) for our code
of conduct.

## References

Hawley, E. and Salisbury, R. (2020). The Himalayan Database.
https://www.himalayandatabase.com/

TidyTuesday (2020). Himalayan Climbing Expeditions.
https://github.com/rfordatascience/tidytuesday/tree/main/data/2020/2020-09-22
