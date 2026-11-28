# Predicting Summit Success in the Nepal Himalaya

**Authors:** Rohan Chakkadath, Laith Saeed, Evan Pai and Harshil Sharma

Data analysis project for DSCI 522 (Data Science Workflows),
as part of UBC's Master of Data Science program.


## Summary

This project asks whether information known before a Himalayan expedition sets off can predict whether a climber will reach the summit. We treat this as a binary classification problem and use supervised machine learning models. The data contain 59,904 member records from 8,420 expeditions in the Nepal Himalaya between 1990 and 2019.

Our final gradient boosting model reached a balanced accuracy of 0.71 on the test set. In cross-validation, logistic regression reached 0.68 (0.65 without the expedition oxygen indicator), and both models clearly outperformed a dummy baseline that always predicts the most frequent outcome (0.50).

These results suggest that planning choices such as hired support and oxygen use carry real information about who reaches the summit, but much of the outcome depends on conditions that cannot be known in advance, so a model like this is better suited to setting realistic expectations than to judging individual climbers.

One important limitation is that the expedition oxygen indicator may be partly recorded after the climb, which would make our results somewhat optimistic. When we removed it, logistic regression's balanced accuracy dropped from 0.68 to 0.65.

## Report

The rendered report is published on GitHub Pages at
<https://ubc-mds-2026-27.github.io/DSCI-522-Group4/>.
Its source is [`analysis/himalayan-summit-prediction.qmd`](analysis/himalayan-summit-prediction.qmd).

## Usage

The analysis runs inside a Docker container, so you do not need to install
Python, uv or Quarto on your own computer. The container image already has
all of them, with the exact versions this project uses.

### Setup

You only need to do these steps once.

1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
   and open it. Docker must be running before you use any of the `docker`
   commands below.

2. Make an ssh key, if you do not already have one, by running this command
   in a terminal and pressing Enter at each question:

   ```bash
   ssh-keygen -t ed25519
   ```

   Check that the file `~/.ssh/id_ed25519.pub` now exists. The container
   reads this key, and if it is missing, Docker creates a folder with that
   name instead, which you would have to delete before making the key.

3. Make sure Git knows your name and email. If
   `git config --global user.email` prints nothing, set them with
   `git config --global user.name "Your Name"` and
   `git config --global user.email "you@example.com"`. The container reads
   your `~/.gitconfig` file, so it must exist before you start it.

4. Clone this repository and move into its folder:

   ```bash
   git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group4.git
   cd DSCI-522-Group4
   ```

5. Download the container image:

   ```bash
   docker compose pull
   ```

   This downloads the image listed in [`docker-compose.yml`](docker-compose.yml)
   from Docker Hub. Docker picks the version that matches your computer's
   processor (Intel/AMD or ARM, such as Apple silicon).

### Running the analysis

From the root of the repository, run:

```bash
docker compose run --rm analysis-env uv run quarto render analysis/himalayan-summit-prediction.qmd
```

This starts a container, renders the report inside it, and then removes the
container when the render finishes (that is what `--rm` does), so there is
nothing to stop or clean up afterwards. The render takes a few minutes (about
3.5 minutes on an Apple silicon Mac, and possibly longer on other computers). It downloads the data again from the TidyTuesday repository, so you
need an internet connection. Because your project folder is shared with the
container, the results appear on your own computer: the data files in
`data/raw/` and `data/processed/`, and the report in
`analysis/himalayan-summit-prediction.html`.

### Changing the project

If you want to change the analysis, work inside the container with Positron,
add a package or republish the report, please follow the instructions in
[`CONTRIBUTING.md`](CONTRIBUTING.md).

## Dependencies

All of the software this project needs runs in a Docker container, so the
only program you need on your own computer is
[Docker](https://www.docker.com/). The container image,
[`rohanchakkadath/dsci-522-group4`](https://hub.docker.com/r/rohanchakkadath/dsci-522-group4),
is built from our [`Dockerfile`](Dockerfile) and published to Docker Hub by a
GitHub Actions workflow. It is based on `rocker/r-ver:4.6.2` and includes
Quarto 1.11.9, uv 0.13.7, Python 3.12.16 and the Python packages pinned in
[`pyproject.toml`](pyproject.toml), with their exact versions locked in
[`uv.lock`](uv.lock).

## AI use statement

Our team used Claude Code (Anthropic), running the Claude Opus 5.5 and Claude Sonnet 5.5 models, for troubleshooting, tutoring, drafting code and text, and proofreading and formatting. All AI-assisted work was reviewed by team members. Please see the [`AI_USAGE.md`](AI_USAGE.md) for a full breakdown of how AI aided in the preparation of this project. 

Example prompts:

- "Review my initial draft for the code of conduct and suggest changes" (with my draft attached)
- "Brief outline on how to draft a CONTRIBUTING.md." / "Brief outline on how to draft a LICENSE.md, what are the key points to keep in mind."
- "Help me organise my data tasks: download the members, expeditions and peaks CSVs, join them, drop the leaky columns, filter to 1990 onward, and do a grouped 70/30 train/test split by expedition."
- "Grammar check. Flag inconsistent punctuation"

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
