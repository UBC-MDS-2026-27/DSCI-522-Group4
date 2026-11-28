# Use of generative AI

This file describes how each team member used generative AI tools in this
project, following the DSCI 522 generative AI policy and our
[CONTRIBUTING guidelines](CONTRIBUTING.md#use-of-generative-ai). Each section
covers that member's use of AI across the whole project, including every
milestone. Members who did not use generative AI say so in their section.

All team members are responsible for the correctness and quality of the work
in this repository, including any part produced with AI assistance.

## Team members

### Rohan Chakkadath

**Tool:** Claude (Opus 5.5). No instruction files were used.

**Used for:**

- Planning the work split and task order for Milestone 1
- - Reviewing my `CODE_OF_CONDUCT.md`, the rendered report and the teamwork contract for errors
  - - Generating initial versions of `CONTRIBUTING.md`, `LICENSE.md`, the data download, cleaning and split code, and the Methods: Data text. I then reviewed, tested and edited each one before committing. While testing, Claude flagged a leaky oxygen column and a duplicated expedition ID.
    - - Help with git commands and with wording issue and PR descriptions
     
      - **Example prompts:**
     
      - - *Code of conduct:* "Review my initial draft for the code of conduct and suggest changes" (with my draft attached)
        - - *Contributing and license:* "Brief outline on how to draft a CONTRIBUTING.md." / "Brief outline on how to draft a LICENSE.md, what are the key points to keep in mind."
          - - *Data work:* "Help me organise my data tasks: download the members, expeditions and peaks CSVs, join them, drop the leaky columns, filter to 1990 onward, and do a grouped 70/30 train/test split by expedition."
            - - *Reviewing:* "Grammar check. Flag inconsistent punctuation"
             
              - ### Harshil Sharma
             
              - **Tools and models**
             
              - - Claude Code (Anthropic), used through the Claude Code extension for VS Code, with the Claude Opus 5.5 model (`claude-opus-5-5`) and, for part of Milestone 1, Claude Sonnet 5.5 (`claude-sonnet-5-5`).
               
                - **What it was used for**
               
                - - *Understanding the requirements:* summarising the milestone instructions, comparing our repository with the course's example project, and checking what was still missing before each submission.
                  - - *Analysis and report:* generating initial versions of the Introduction and the exploratory data analysis code and text, and refining the figures. I reviewed the rendered report and checked every figure before committing.
                    - - *Proofreading:* checking the rendered report and teammates' sections for errors and inconsistencies.
                      - - *Troubleshooting:* diagnosing environment problems, such as an outdated version of uv that could not install the pinned Python version.
                       
                        - I reviewed all AI-assisted code and text, and I am able to explain it.
                       
                        - **Instructions given to the tool**
                       
                        - I did not use a project instruction file.
                       
                        - **Example prompts** (paraphrased)
                       
                        - - "Compare our repository with the example project and outline how we should structure the analysis and split the work."
                          - - "Build exploratory figures on the training set and explain what each one shows about summit success."
                            - - "Fix the year axis formatting and move the legend so it is fully visible."
                             
                              - ### Evan Pai
                             
                              - **Tools and models**
                             
                              - - Claude Code (Anthropic), with the Claude Opus 5.5 model
                                - (`claude-opus-5-5`), used through the Claude Code extension for VS Code.
                               
                                - **What it was used for**
                               
                                - - *Understanding the requirements:* summarising the milestone instructions and
                                  - the course policies, and checking the repository against the requirements
                                  - before submission.
                                  - - *Computational environment:* setting up and testing the project's
                                    - environment, and checking that the report renders from a fresh copy of the
                                    - repository by following our instructions exactly.
                                    - - *Analysis and report:* drafting code and text for the parts of the analysis I
                                      - was responsible for, following the plan agreed by the team. After each step,
                                      - the report was rendered and the numbers in the text were checked against the
                                      - tables and figures.
                                      - - *Documentation:* drafting parts of the project documentation, and testing the
                                        - steps it describes before committing.
                                        - - *References:* confirming that the references I added exist and support the
                                          - statements they are cited for.
                                          - - *Git and GitHub workflow:* explaining branches, pull requests and code
                                            - review, and creating local commits on my feature branches, with me as the
                                            - author, after I reviewed the changes.
                                            - - *Issues and pull requests:* drafting the wording of issues, pull request
                                              - descriptions and review comments. I reviewed and edited the text, and opened
                                              - the issues and pull requests and submitted the reviews myself.
                                             
                                              - I reviewed all AI-assisted code and text, and I am able to explain it.
                                             
                                              - **Instructions given to the tool**
                                             
                                              - I did not use a project-specific instruction file. Claude Code also read my
                                              - personal global settings file (`~/.claude/CLAUDE.md`), which applies to all of
                                              - my projects. It is not committed here because it contains personal contact
                                              - details.
                                             
                                              - **Example prompts** (originally in Chinese, translated)
                                             
                                              - - "Summarise what we need to do for this milestone."
                                                - - "Create the environment files and set them up, check that everything works
                                                  - and tell me what you did. Don't push yet."
                                                  - - "Tell me the complete steps for the modelling part, starting from the
                                                    - issues."
                                                    - - "Write the modelling part. Check the implementation, and make the commits on
                                                      - a new branch."
                                                      - - "Check what is still missing for this milestone and what needs to wait for my
                                                        - teammates."
                                                       
                                                        - ### Laith Saeed
                                                       
                                                        - **Tools and models**
                                                       
                                                        - - Claude Code (Anthropic), used in the terminal (command-line version), with
                                                          - the Claude Opus 5.5 model (`claude-opus-5-5`).
                                                         
                                                          - **What it was used for**
                                                         
                                                          - - *Understanding the project:* comparing our repository with the course's
                                                            - example project, summarising the Milestone 1 instructions, and checking
                                                            - which requirements were still missing.
                                                            - - *Tutoring:* explaining how Quarto documents run Python code, how to run the
                                                              - report chunk by chunk in Positron, what each code chunk in the report does,
                                                              - and how GitHub issues, branches and pull requests fit together.
                                                              - - *Reviewing teammates' work:* rendering the report from the modelling
                                                                - branches to check that it ran without errors before I reviewed and merged
                                                                - PRs #11, #13, #15 and #17, and pointing out wording that breaks the
                                                                - milestone writing rules.
                                                                - - *Proofreading and formatting:* fixing spelling, spacing and formatting
                                                                  - errors in the team contract, and rewording the sections I asked to change.
                                                                  - I reviewed every change before submitting the contract.
                                                                  - - *README:* drafting the structure and factual sections of the README (setup
                                                                    - and render commands, dependencies, licenses), and correcting the grammar of
                                                                    - the Summary and AI use statement I wrote.
                                                                   
                                                                    - **Actions the tool took on GitHub**
                                                                   
                                                                    - None. I opened all of my issues (#24 to #27) and reviewed, approved and
                                                                    - merged PRs #11, #13, #15 and #17 myself. Claude Code only ran read-only git commands
                                                                    - on my computer (such as `git status`, `git log` and `git fetch`), read public
                                                                    - pages of our repository, and once made a temporary local copy of the
                                                                    - repository to test that the report renders.
                                                                   
                                                                    - I reviewed all AI-assisted work, and I am able to explain it.
                                                                   
                                                                    - **Instructions given to the tool**
                                                                   
                                                                    - I did not use a project instruction file. I set up local Claude Code settings
                                                                    - on my computer (not committed) that block it from running any git command
                                                                    - that changes the repository and from using the GitHub command line tool.
                                                                   
                                                                    - **Example prompts**
                                                                   
                                                                    - - "I need your help to not only make sure our project is good to submit but
                                                                      - also to explain the various code chunks to me."
                                                                      - - "Go through the contract fixing any spacing or typos you see please."
                                                                        - - "I am giving you permission to run git commands to view only. I don't want
                                                                          - you making any commits, deleting any branches etc."
                                                                          - - "Take a look at the README.md. Please don't nitpick, just ensure it's
                                                                            - grammatically accurate and call out major issues."
                                                                            - 
