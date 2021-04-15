# Scientific project template

### Overview 
This is a generic template to serve as reference for simple scientific projects.

The general structure is as follows:
- `dat`: data sets
- `dev`: development (scripts)
- `doc`: documentation
- `org`: organizational stuff
- `plt`: plots / figures

In addition, generic `.gitignore` and `.Rproj` files are included. 

Further reading:
- Noble (2009): [A Quick Guide to Organizing Computational Biology Projects](https://doi.org/10.1371/journal.pcbi.1005510).
- Wilson et al. (2017): [Good enough practices in scientific computing](https://doi.org/10.1371/journal.pcbi.1000424).

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
   
