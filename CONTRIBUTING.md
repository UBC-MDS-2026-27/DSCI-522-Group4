# Contributing to Predicting Summit Success in the Nepal Himalaya

Thank you for your interest in contributing! This project was created by
Rohan Chakkadath, Laith Saeed, Evan Pai, and Harshil Sharma as part of DSCI 522
(Data Science Workflows) in the Master of Data Science program at the University
of British Columbia. We welcome contributions from anyone, whether it is
reporting a bug, suggesting an improvement, or fixing something yourself.

By participating in this project, you agree to follow our
[Code of Conduct](CODE_OF_CONDUCT.md).

## Ways to contribute

- **Report a bug:** something does not run, gives an error, or produces a
  result that looks wrong.
- **Suggest a change:** an idea for improving the analysis, the report, or the
  documentation.
- **Submit your own work:** a fix, a new feature, or a documentation
  improvement through a pull request.

## Reporting a bug

Before opening a new issue, please search the existing
[issues](https://github.com/UBC-MDS-2026-27/DSCI-522-Group4/issues) to check
that the problem has not already been reported.

If it has not, open a new issue and include:

- a short, descriptive title (e.g., "Report fails to render on Windows")
- the steps you followed, so that we can reproduce the problem
- what you expected to happen, and what actually happened
- the full error message, if there is one
- your operating system and the version of the project you were using (e.g.,
  release `0.0.1` or a commit hash)

## Suggesting a change

To suggest an improvement, open an
[issue](https://github.com/UBC-MDS-2026-27/DSCI-522-Group4/issues) that
describes the change and explains why it would be useful. For larger changes,
please wait for a team member to respond before you start working on it, so
that we can agree on the approach first.

## Submitting your work

### Setting up

All work on this project happens inside our Docker container, so you do not
install Python, uv or Quarto on your own computer. First, follow the
[Setup steps in the README](README.md#setup): install Docker Desktop, make an
ssh key, check your Git name and email, clone the repository, and run
`docker compose pull`. Then follow the steps below to work in the container.

### Working in the container with Positron

We edit and run the project in [Positron](https://positron.posit.co/),
connected to the container over ssh. Your project folder is shared with the
container, so a file you change in the container also changes on your own
computer.

**Once, before your first connection**, install Positron. Its Remote SSH
feature, which connects to the container, is built in, so you do not need an
extension. Also check that you have done every README setup step: the
container needs your ssh key to let you log in, and your `~/.gitconfig` file
so that the commits you make in the container are recorded under your name.

**Each time you work on the project:**

1. Open Docker Desktop. In a terminal, in the project folder, start the
   container in the background:

   ```bash
   docker compose up -d
   ```

   `docker compose ps` should list `analysis-env` as running.

2. In Positron, open the Command Palette (`Cmd+Shift+P` on Mac,
   `Ctrl+Shift+P` on Windows), run **Remote SSH: Show Remote Menu**, and pick
   **Connect to Host**.

3. Type `root@localhost:2222` and press Enter. A new Positron window opens.
   If it asks for the platform of the remote host, pick **Linux**. If it asks
   whether you trust the host's fingerprint, click **Continue**. The first
   time, Positron installs its server inside the container, which can take
   several minutes.

4. Open the project folder. The Explorer first says "No folder opened",
   because the container starts in its home folder, `/root`. Click
   **Open Folder**, replace the path with `/workspace`, and press Enter (you
   may need to click **OK** a few times). When Positron asks whether you trust
   the authors of the files in this folder, click **Trust**. Until you do, the
   folder is in Restricted Mode, and the Python extension and consoles do not
   work.

5. Pick the right Python interpreter. Check this every time, because Positron
   often starts a different one:

   - Positron may start an R console first, because the container's base image
     also includes R. Our project only uses Python, so switch to Python.
   - The interpreter list does not show the project's environment. It marks
     `./.venv` as "Recommended", but that is the environment from your own
     computer and it does not run in the container. It also offers a global
     Python 3.12, which has none of our packages. Do not pick either of these.
   - Instead, open the Command Palette, run **Python: Select Interpreter**,
     choose **Enter interpreter path...**, and type `/opt/venv/bin/python`.
     This is the environment built from our `uv.lock`. Then start a new
     console with it.
   - If Positron asks "Create a virtual environment for this workspace?",
     click **Never for This Interpreter**. Also ignore the
     **Create Python Environment** button on the Welcome page.

   To check, run `import sys; print(sys.executable)` in the Console. It
   should print `/opt/venv/bin/python`.

6. Work as usual. Before you do anything, check that the window title shows
   `[SSH: localhost:2222]`, especially if you also have a Positron window open
   on your own computer. The Terminal, Console and Render button in this
   window all run inside the container. To render the report from the
   Terminal, run:

   ```bash
   uv run quarto render analysis/himalayan-summit-prediction.qmd
   ```

   You can commit and push from the container's Terminal as usual. The first
   time you push, GitHub may ask you to sign in through a browser window that
   Positron opens. Positron remembers this afterwards.

7. When you are done, close the Positron window, then stop the container from
   a terminal on your own computer:

   ```bash
   docker compose down
   ```

**If it does not connect:**

- *`~/.ssh/id_ed25519.pub` is a folder:* Docker made it because the key did not
  exist yet. Run `docker compose down`, delete that folder, make the key (see
  the README), and start again.
- *`~/.gitconfig` is a folder, or Git in the container does not know your
  name:* the same thing happened with your Git settings. Run
  `docker compose down`, delete that folder, set your Git name and email (see
  the README), and start again.
- *It asks for a password:* the container cannot see your key. Check that your
  key is named `id_ed25519.pub`, or change the key path in
  `docker-compose.yml`.
- *"Remote host identification has changed":* you are using a new image. Run
  `ssh-keygen -R "[localhost]:2222"` and connect again.
- *Port 2222 is already in use:* change the first `2222` in
  `docker-compose.yml` to another number, such as `2223`, and connect to that
  port instead.
- *Linux laptops:* ssh refuses the key because the file belongs to you, not
  `root`. Remove the `#` from the `StrictModes no` line in the `Dockerfile` and
  push it, so that the workflow publishes a fixed image.

### Adding or updating a package

The container image is built from our `Dockerfile`, `pyproject.toml` and
`uv.lock`, so adding a package means publishing a new image. Every package in
`pyproject.toml` must be pinned to an exact version with `==`.

1. On a new branch, in the container's Terminal, add the package with an
   exact version:

   ```bash
   uv add --bounds exact <package-name>
   ```

   `--bounds exact` makes uv write the package with `==` in `pyproject.toml`.
   Commit `pyproject.toml` and `uv.lock` together and push the branch.

2. The push starts the **Publish image to Docker Hub** workflow on GitHub
   Actions. It builds the new image for Intel/AMD and ARM computers, publishes
   it on Docker Hub, and commits the new image tag to `docker-compose.yml` on
   your branch. Wait until the run on the **Actions** tab has finished.

3. Get that commit and the new image, then restart the container:

   ```bash
   git pull
   docker compose pull
   docker compose down
   docker compose up -d
   ```

4. Check that the report still renders, then open a pull request. When it is
   merged, the workflow runs once more on `main` and commits another new tag.
   When that run has finished, everyone runs `git pull` on `main` and
   `docker compose pull` again.

Do not turn on branch protection for `main`: the workflow commits the new
image tag directly to the branch, and branch protection would block it.

### Republishing the report

The report on GitHub Pages is a copy of the rendered report, served from the
`docs/` folder on `main`. Each time you re-render the report, copy it into
`docs/` again and include it in your pull request:

```bash
uv run quarto render analysis/himalayan-summit-prediction.qmd
cp analysis/himalayan-summit-prediction.html docs/index.html
```

Commit both `analysis/himalayan-summit-prediction.html` and
`docs/index.html`. Do not delete `docs/.nojekyll`, which tells GitHub Pages to
serve the file as it is. After your pull request is merged, check that
<https://ubc-mds-2026-27.github.io/DSCI-522-Group4/> shows the updated report.

### Workflow

We use the [GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow)
workflow. Nobody pushes directly to `main`.

1. **Team members** create a new branch in this repository. **External
   contributors** should first
   [fork the repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)
   and create the branch in their fork.
2. Give the branch a name that describes the work, such as `add-eda-plot` or
   `fix-readme-typo`, rather than `branch1` or your own name.
3. Keep each branch small and focused on one independent piece of work.
4. Commit often, with meaningful commit messages (see below).
5. Push your branch and open a pull request against `main`. In the description,
   explain what you changed and why, and link any related issue (e.g.,
   "Closes #12").
6. At least one team member other than the author must review and approve the
   pull request before it is merged.

### Before you open a pull request

Please check that:

- the report renders without errors inside the container
- any new dependencies have been added with `uv add --bounds exact`, and the
  new image tag is in `docker-compose.yml`
- if you re-rendered the report, `docs/index.html` has been updated too
- data is downloaded and processed by code, not added to the repository by hand
- no drafts, scratch files, or system files (e.g., `.DS_Store`) are included

### Commit messages

Write commit messages that briefly say what the commit does, in the imperative
mood. For example, "Add histogram of training data to EDA section" is helpful;
"update" or "changes" is not.

### Reviewing pull requests

Reviewers should pull the branch, check that the report still renders, and
leave specific, constructive comments. Ask questions if something is unclear,
and explain the reasoning behind any requested changes.

## Use of generative AI

Contributors may use generative AI tools (e.g., ChatGPT, Claude, GitHub
Copilot) to help with their work, within the rules below.

**Allowed uses** include brainstorming ideas, explaining error messages,
drafting code or text that you then review and edit, and double-checking code
before you submit or review a pull request.

**Not allowed:**

- Issues, pull requests, and pull request reviews must be opened, written, and
  approved by a person, not by an AI agent or chatbot. Only human reviewers may
  approve and merge pull requests.
- Do not submit AI-generated code or text that you do not understand or have
  not checked.
- Do not add references suggested by an AI tool without confirming that the
  source exists and supports the claim it is cited for.
- Do not paste passwords, access tokens, or other private information into AI
  tools.

**Disclosure:** If you used generative AI for a contribution, say so in the
pull request description, naming the tool and briefly describing what you used
it for. If you used an instruction file (e.g., `CLAUDE.md`), commit it to the
repository and mention it in the [README](README.md).

**Responsibility:** You are fully responsible for everything you submit,
including any part produced with AI assistance. You should be able to explain
every line of your contribution to a reviewer.

## Questions

If you have a question that is not covered here, please open an
[issue](https://github.com/UBC-MDS-2026-27/DSCI-522-Group4/issues) and a team
member will get back to you.