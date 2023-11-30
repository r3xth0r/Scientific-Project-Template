# Scientific project template

This is a dummy project to be used as a template to maintain a standardized project structure.

## Table of Contents
- [How to use](#How-to-use)
- [Overview](#template-overview)
- [Conventions](#conventions)
    - [Files](#files)
    - [Workflow](#workflow)
    - [Coding style](#coding-style)
    - [Visualization](#visualization)
    - [Commit messages](#commit-messages)
- [Basic git commands](#basic-git-commands)

&nbsp;

## How to use
There are two alternatives to use this template as a blueprint for your own project:

1. Simply [fork](https://docs.gitlab.com/ee/user/project/repository/forking_workflow.html) the repo
2. Clone the repo and change the upstream remote:
   ```sh
   git clone git@gitlab.com:Rexthor/scientific-project-template.git foobar
   git remote set-url origin git@gitlab.com:Rexthor/scientific-project-template.git
   ```
   Double check with `git remote -v`, then `git push`.

&nbsp;


## Template overview 
This is a generic template to serve as reference for simple scientific projects.

The general structure is as follows:
- `dat`: data sets
- `dev`: development (scripts)
- `doc`: documentation (e.g. reports, dissemination)
- `gis`: GIS projects
- `org`: organizational stuff (e.g. contract, accounting)
- `plt`: plots / figures

Specifically, the data folder `dat` is structured as follows:

```sh
dat
├── interim    » Intermediate data that has been transformed.
├── processed  » Canonical output data sets.
├── raw        » The original, immutable data dump.
└── reporting  » Final data sets for delivery/reporting.
```

In addition, generic `.gitignore` and `.Rproj` files are included. 

Remarks:
- Use [pre-commit](https://pre-commit.com/) hooks. A sample `.pre-commit-config.yaml` is provided. Run `pre-commit install` to install/set up the hooks specified in the configuration file.


Further reading:
- Noble (2009): [A Quick Guide to Organizing Computational Biology Projects](https://doi.org/10.1371/journal.pcbi.1005510).
- Wilson et al. (2017): [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1000424).

For additional information on project structure see:
- [Cookiecutter](https://github.com/cookiecutter/cookiecutter)
- [Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/)


&nbsp;


## Conventions

#### Files

**Filenames**
- File names should be meaningful and concise. Avoid excessively long filenames.
- Avoid blanks. Use underscores (`_`) or dashes (`-`).
- Avoid special characters
- Start the filename with the current timestamp if feasible: `YYYY-MM-DD_filename.end`
- If files need to be run in sequence, prefix them with (two) numbers: `01-download_data.py`  

**Filetypes**
- If possible, use geopackages instead of shapefiles
- If you use shapefiles, put them in dedicated folders
- Use [Arrow](https://arrow.apache.org/docs/) when seeking to access files in both R and Python.


#### Workflow
- If possible, use scripts as much as possible - for the sake of reproducibility and automation. This is especially true for GIS operations.
- If files need to be run in sequence, prefix them with (two) numbers
- Consider using tools like [drawio](https://app.diagrams.net/) for illustrating your workflows. Check in the xml file for documentation purposes.


#### Coding style
**Python**
- Use [`black`](https://github.com/psf/black) as autoformatter
- Recommended editor: [VSCode](https://code.visualstudio.com/docs/python/python-tutorial)

**R**
- [tidyverse style guide](https://style.tidyverse.org/)
- Use `tidyverse`
- Use `sf` for vector data
- Recommended editor:
    - [RStudio](https://www.rstudio.com/)
    - [VScode](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) w/ [radian](https://github.com/randy3k/radian)


#### Visualization
- Use of colors: For color coding data visualizations it is crucial to choose a palette that appropriately captures the underlying information. Please refer to color palettes as provided in the [HCL Wizard](https://hclwizard.org/) and use the respective `colorspace`  packages for [R](http://colorspace.r-forge.r-project.org/) and [Python](https://python-colorspace.readthedocs.io/en/latest/).
- Color advice for maps is available at the [Color Brewer](https://colorbrewer2.org/).
- Check out [Question-based visualizations](https://graphicsprinciples.github.io/qbv.html) for help on visualizing the underlying scientific questions of interest clearly and explicitly.


#### Commit messages

![commit](https://imgs.xkcd.com/comics/git_commit.png)

- Commit messages should be clear and unambiguous.
- They can contain more than one line to explain the change if needed, which will not be visible in commit overviews, but in the detailed views.
- Please use imperative present tense for commit messages and avoid dots at the end.
- It is quite common to use short abbreviations at the beginning of commit messages declaring what type of changes the commit contains (c.f. list from [Numpy developement workflow](https://docs.scipy.org/doc/numpy-1.15.1/dev/gitwash/development_workflow.html#writing-the-commit-message)).
- Please use the following prefixes for commit messages:
  - `API:` an (incompatible) API change
  - `BUG:` bug fix
  - `DEP:` deprecate something, or remove a deprecated object
  - `DEV:` development (tool or utility)
  - `DOC:` documentation
  - `MNT:` maintenance (e.g. renaming files)
  - `REF:` code refactoring
  - `REV:` revert an earlier commit
  - `STY:` style changes / formatting
  - `TST:` addition or modification of tests
- Certain references in GitLab can be added automatically (copied from help):
  - @foo : for team members
  - @all : for the whole team
  - #123 : for issues
  - !123 : for merge requests
  - $123 : for snippets
  - 1234567 : for commits
  - \[file\]\(path/to/file\) : for file references

&nbsp;


## Basic git commands
- `git status`: list files you've changed and those you still need to add or commit
- `git add <file>`: add <file> to staging (index)
- `git commit -m "Commit message"`: commit changes to head
- `git fetch`: fetch changes from remote
- `git merge`: merge changes from remote to local (also: merge branches)
- `git pull`: `git fetch` & `git merge` (not recommended)
- `git push`: send changes made in local version to remote
- `git log`: show all commits
- `git log -p <file>`: show changes over time for a specific file
- `git blame <file>`: who changed what and when in <file>
- `git stash`: stash the changes in a dirty working directory away
- `git stash pop`: apply stashed state on top of current working directory state

