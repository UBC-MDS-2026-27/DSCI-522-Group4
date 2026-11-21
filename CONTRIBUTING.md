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

Clone the repository and set up the computational environment with
[uv](https://docs.astral.sh/uv/):

    git clone https://github.com/UBC-MDS-2026-27/DSCI-522-Group4.git
    cd DSCI-522-Group4
    uv sync

To render the report, run this from the root of the repository:

    uv run quarto render analysis/himalayan-summit-prediction.qmd

If your change needs a new package, add it with `uv add <package-name>` so that
`pyproject.toml` and `uv.lock` stay up to date, and commit both files.

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

- the report renders without errors
- any new dependencies have been added to the environment files
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