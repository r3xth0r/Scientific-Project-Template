# Scientific project template


### Overview 
This is a generic template to serve as reference for simple scientific projects.

The general structure is as follows:
- `dat`: data sets
- `dev`: development (scripts)
- `doc`: documentation (e.g. reports, dissemination)
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

Further reading:
- Noble (2009): [A Quick Guide to Organizing Computational Biology Projects](https://doi.org/10.1371/journal.pcbi.1005510).
- Wilson et al. (2017): [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1000424).

For additional information on project structure see:
- [Cookiecutter](https://github.com/cookiecutter/cookiecutter)
- [Cookiecutter Data Science](https://drivendata.github.io/cookiecutter-data-science/)


### Commit message conventions
- Commit messages should be clear and unambiguous.
- Please use imperative present tense for commit messages and avoid dots at the end.
- Please use the following prefixes for commit messages (see [Numpy developement workflow](http://docs.scipy.org/doc/numpy/dev/gitwash/development_workflow.html#writing-the-commit-message))
   - `BUG:` bug fix
   - `DAT:` add/edit data set
   - `DEP:` deprecate something, or remove a deprecated object
   - `DEV:` code development
   - `DOC:` documentation
   - `MNT:` maintenance
   - `REF:` code refactoring
   - `REV:` revert an earlier commit
   - `STY:` style changes / formatting
   
