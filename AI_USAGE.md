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

*To be added by Rohan.*

### Harshil Sharma

**Tools and models**

- Claude Code (Anthropic), used through the Claude Code extension for VS Code.
  It ran on the Claude Opus 5.5 model (`claude-opus-5-5`) for most of my work
  and on Claude Sonnet 5.5 (`claude-sonnet-5-5`) for the last part.

**What it was used for**

- *Planning:* reading the DSCI 522 breast cancer predictor template (release
  0.0.1) and suggesting how to split the work and structure the report.
- *Introduction and exploratory data analysis (PR #6):* drafting the code and
  text for the Introduction and the exploratory data analysis section,
  computing the statistics quoted in the text, finding the references (Preiss
  2018, Altair, NumPy), and rendering the report to check the figures.
- *Review fixes:* checking Rohan's review comments on PR #6 against the data
  and making the three fixes.
- *Reviewing teammates' work:* checking PRs #3, #5, #7, #11, #13, #15 and #17
  by rendering the report and comparing the text with the output, and
  checking the references.
- *Git and GitHub:* creating the branches and commits for my work, and
  installing the GitHub command line tool.

**Actions the tool took on GitHub using my account**

I asked Claude Code to act on GitHub for me, and it did so using my account.
It opened PR #6, posted my reply to Rohan's review on PR #6, merged PR #6 after
Rohan approved it, and submitted my approval of PR #3. It also opened issues
#18 to #22, submitted my reviews on PRs #11, #13, #15 and #17, and opened the
pull request that adds this section. I asked for each of these actions and
checked the results. Some of these actions, such as merging PR #6 and
submitting my reviews, do not follow the rule in our CONTRIBUTING guidelines
that issues, pull requests and reviews must be opened, written and approved by
a person. I am disclosing this here so that the record is accurate.

I reviewed all AI-assisted code and text, and I am able to explain it.

**Instructions given to the tool**

I did not use a project instruction file.

**Example prompts**

- "Go through the example repo and tell me how we should proceed as a group of
  four."
- "I am taking part B, so I'll also write the Introduction. Let's get started."
- "Check the comment Rohan left on the PR."
- "Make the changes and reply to Rohan."
- "Check that everything Rohan asked me to review is correct, then I'll review
  it."


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

**Tools and models**

- Claude Code (Anthropic), used in the terminal (command-line version), with
  the Claude Opus 5.5 model (`claude-opus-5-5`).

**What it was used for**

- *Understanding the project:* comparing our repository with the course's
  example project, summarising the Milestone 1 instructions, and checking
  which requirements were still missing.
- *Tutoring:* explaining how Quarto documents run Python code, how to run the
  report chunk by chunk in Positron, what each code chunk in the report does,
  and how GitHub issues, branches and pull requests fit together.
- *Reviewing teammates' work:* rendering the report from the modelling
  branches to check that it ran without errors before I reviewed and merged
  PRs #11, #13, #15 and #17, and pointing out wording that breaks the
  milestone writing rules.
- *Proofreading and formatting:* fixing spelling, spacing and formatting
  errors in the team contract, and rewording the sections I asked to change.
  I reviewed every change before submitting the contract.
- *README:* drafting the structure and factual sections of the README (setup
  and render commands, dependencies, licenses), and correcting the grammar of
  the Summary and AI use statement I wrote.

**Actions the tool took on GitHub**

None. I opened all of my issues (#24 to #27) and reviewed, approved and
merged PRs #11, #13, #15 and #17 myself. Claude Code only ran read-only git commands
on my computer (such as `git status`, `git log` and `git fetch`), read public
pages of our repository, and once made a temporary local copy of the
repository to test that the report renders.

I reviewed all AI-assisted work, and I am able to explain it.

**Instructions given to the tool**

I did not use a project instruction file. I set up local Claude Code settings
on my computer (not committed) that block it from running any git command
that changes the repository and from using the GitHub command line tool.

**Example prompts**

- "I need your help to not only make sure our project is good to submit but
  also to explain the various code chunks to me."
- "Go through the contract fixing any spacing or typos you see please."
- "I am giving you permission to run git commands to view only. I don't want
  you making any commits, deleting any branches etc."
- "Take a look at the README.md. Please don't nitpick, just ensure it's
  grammatically accurate and call out major issues."

