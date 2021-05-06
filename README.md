# Scientific project template
This is a dummy project that can be cloned as a template to maintain a standardized project structure.

## Table of Contents
- [Checklist](#checklist-for-new-projects)
- [Overview](#template-overview)
- [Conventions](#conventions)


&nbsp;


## Checklist for new projects

For each new project, please:
1. fork this repo
1. add new [project group label](https://vgitlab.zamg.ac.at/groups/zamg-eo/-/labels) named `Project: {shortname}` with color `#666666`
1. create meta-issue in [Meta](https://vgitlab.zamg.ac.at/zamg-eo/meta/-/issues) repo 
1. setup work packages as milestones and tasks as issues
1. setup new project on share


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
├── external   » Data from third party sources.
├── interim    » Intermediate data that has been transformed.
├── processed  » The final, canonical data sets for modeling.
└── raw        » The original, immutable data dump.
```

In addition, generic `.gitignore` and `.Rproj` files are included. 

Remarks:
- Please maintain this structure consistently on the repo and on the share.
- All code should be commited to the repo (`dev` could be empty on the share).
- Please DO NOT commit large data sets (e.g. small csv files are fine), reports, plots/images, spreadsheets etc. These should reside on the share.


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


#### Commit message conventions
- Commit messages should be clear and unambiguous.
- Please use imperative present tense for commit messages and avoid dots at the end.
- Please use the following prefixes for commit messages (see [Numpy developement workflow](http://docs.scipy.org/doc/numpy/dev/gitwash/development_workflow.html#writing-the-commit-message)). See the [GitLab Howto](https://vgitlab.zamg.ac.at/zamg-eo/meta/-/wikis/Setup/gitlab_howto#commit-message-conventions) on the wiki for details.
