# Use of generative AI

This file records how each team member used generative AI tools in this
project, following the DSCI 522 generative AI policy and our
[CONTRIBUTING guidelines](CONTRIBUTING.md#use-of-generative-ai). Each member
writes their own section and updates it as the project evolves. Members who
did not use generative AI for a milestone state that in their section.

All team members are responsible for the correctness and quality of the work
in this repository, including any part produced with AI assistance.

## Milestone 1

### Rohan Chakkadath

**Tool:** Claude (Opus 5.5). No instruction files were used.

**Used for:**

- Planning the work split and task order for Milestone 1
- Reviewing my `CODE_OF_CONDUCT.md`, the rendered report and the teamwork contract for errors
- Generating initial versions of `CONTRIBUTING.md`, `LICENSE.md`, the data download, cleaning and split code, and the Methods: Data text. I then reviewed, tested and edited each one before committing. While testing, Claude flagged a leaky oxygen column and a duplicated expedition ID.
- Help with git commands and with wording issue and PR descriptions

**Example prompts:**

- *Code of conduct:* "Review my initial draft for the code of conduct and suggest changes" (with my draft attached)
- *Contributing and license:* "Brief outline on how to draft a CONTRIBUTING.md." / "HBrief outline on how to draft a LICENSE.md, what are the key points to keep in mind."
- *Data work:* "Help me organise my data tasks: download the members, expeditions and peaks CSVs, join them, drop the leaky columns, filter to 1990 onward, and do a grouped 70/30 train/test split by expedition."
- *Reviewing:* "Grammar check. Flag inconsistent punctuations"

### Harshil Sharma

**Tool:** Claude Code (Opus 5.5 and Sonnet 5.5). No instruction files were used.

**Used for:**

- Understanding the Milestone 1 requirements and planning how to structure the
  analysis, using the course's example project as a reference
- Generating initial versions of the Introduction and the exploratory data
  analysis code and text, then refining the Altair figures (consistent colours,
  readable axes, legend placement and layout). I reviewed the rendered report
  and checked the figures before committing.
- Checking that the statistics quoted in the text matched the training data and
  that the cited sources exist and support the claims
- Proofreading the rendered report and teammates' sections for errors and
  inconsistencies

**Example prompts:**

- *Planning:* "Go through the example project and outline how we should
  structure our analysis and split the work."
- *EDA:* "Build exploratory figures on the training set and explain what each
  one shows about summit success."
- *Visualisation:* "Fix the year axis formatting and move the legend so it is
  fully visible."
- *Proofreading:* "Check my text for errors and remove long dashes."

### Evan Pai

**Tools and models**

- Claude Code (Anthropic), Claude Opus 5.5 model (`claude-opus-5-5`), used
  through the Claude Code extension for VS Code.

**What it was used for**

- *Understanding the requirements:* summarising the Milestone 1 instructions,
  the teamwork contract template and the course policies, and checking the
  repository against the milestone requirements.
- *Computational environment (PR #1):* testing that the report renders with
  the uv environment, adding the packages Quarto needs to run Python code
  (`pyyaml`, `nbformat`, `nbclient`), writing `.gitignore`, creating the
  project folders, writing the environment setup section of the README, and
  checking that the environment can be rebuilt from `uv.lock` in a fresh
  folder.
- *Git and GitHub workflow:* explaining branches, pull requests, code review
  and how to merge stacked pull requests.
- *Analysis and report (PRs #11, #13 and #15):* drafting the code and text for
  the modelling part of Methods and for the Results, Discussion and Summary
  sections, following the analysis plan agreed by the team. This covers the
  preprocessing pipeline, the baseline, logistic regression, the comparison
  with and without expedition oxygen use, gradient boosting, the model
  comparison, and the test set evaluation. After each step, the report was
  rendered and every number in the text was checked against the tables and
  figures.
- *References:* confirming through Crossref and the publisher's page that the
  added references (Pedregosa et al. 2011; Huey et al. 2020) exist and support
  the statements they are cited for.
- *Commits:* creating local commits on my feature branches, with me as the
  author, after I reviewed the changes.
- *Issues and pull requests:* drafting the English wording of issues #8, #9
  and #10, the handover issue for the remaining Milestone 1 tasks, the
  descriptions of PRs #11, #13 and #15, and my review comment on PR #7, based
  on the team's task plan. I reviewed and edited the text, and opened the
  issues and pull requests and submitted the review myself.

I reviewed all AI-assisted code and text, and I am able to explain it.

**Instructions given to the tool**

I did not use a project-specific instruction file. Claude Code also read my
personal global settings file (`~/.claude/CLAUDE.md`), which applies to all of
my projects. It is not committed here because it contains personal contact
details. 

**Example prompts** (originally in Chinese, translated)

- "Summarise what we need to do for this milestone."
- "Create the environment files and set them up, check that everything works
  and tell me what you did. Don't push yet."
- "Tell me the complete steps for the modelling part, starting from the
  issues."
- "Write part C. Check the implementation, and make the commits on a new
  branch."
- "Check what is still missing for Milestone 1 and what needs to wait for my
  teammates."



### Laith Saeed

*To be added by Laith.*

