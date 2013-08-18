Notes-Git
=========

## Git

`$ git clone /path/to/repository` clones repository to current folder

`$ git pull origin master` updates local data from repository

`$ git add --all` add all files to the commit

`$ git commit -a -m "Commit message"`commit merged file after conflict is solved

`$ git push origin master` push committed date to repository


### Ignoring files with .gitignore

In git, ignore *rules* can be specified to exlude certain files or file types from your commits. This *rules* are specified in the .gitignore file, on the root folder for the whole project or in sub-folders for folder-specific *rules*.

#### Ignore file-types

.gitignore file to ignore the .bak, .dwl and .dwl2 file-types

```
*.bak
*.dwl
*.dwl2
```

#### Ignore specific files

.gitignore file to ignore specific files named .DS_Store, Thumbs.db

```
.DS_Store
Thumbs.db
```

#### Downloads

* [WIN](https://code.google.com/p/msysgit/downloads/list?q=full+installer+official+git)


## Terminal

Notes on git and terminal commands.

`alias desktop='cd /Users/nono/Desktop'` Create an alias or shortcut for a command on the terminal


## git-ftp

To have the correct version on OS X, we can install git-ftp with homebrew as follows:

```
brew tap homebrew/dupes
brew install grep
```