Notes-Git
=========
Notes on basic concepts of Git.

## Git

`$ git clone /path/to/repository` clones repository to current folder

`$ git pull origin master` updates local data from repository

`$ git add --all` add all files to the commit

`$ git commit -m "Commit message"` commit all the changes done to *previously added* files  

`$ git commit -a -m "Commit message"`commit merged file after conflict is solved  

`$ git push origin master` push committed date to repository  

`git rm README.md` removes README.md  

`git mv README.txt README.md` Renames the file README.txt to README.md  

`git status` outputs the status of the repository  

**Stashing Changes**

When you have done `git add --all`, for instance, all your changes would be sent on a new `git commit ...`. If you want to go back to HEAD—the state of your repository on your previous commit—you can stash your changes and they get saved to a `stash@{x}`.

`git stash [save]`  
`git stash apply [stash@{x}]` (`stash@{0}` by default) applies the changes on stash keeping the stash@{x}  
`git stash pop [stash@{x}]` (`stash@{0}` by default) applies the changes on stash popping the stash@{x}

**Start a New Repository Locally**

`cd my_project`  
`git init`  
`git add *`  
`git commit -m "My initial commit message"`  
`git remote add origin git@example.com:my_project.git`  
`git push -u origin master`  


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

#### Keep Your Fork Up-to-date

*From: <https://gist.github.com/CristinaSolana/1885435>*

1. Clone your fork:

    git clone git@github.com:YOUR-USERNAME/YOUR-FORKED-REPO.git

2. Add remote from original repository in your forked repository: 

    cd into/cloned/fork-repo
    git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
    git fetch upstream

3. Updating your fork from original repo to keep up with their changes:

    git pull upstream master

#### Log

List commits `git log --pretty=oneline`  

#### Tags

Add tag `git tag -a "1.0" -m "Message is here, can have line breaks."`  
Add tag to specific commit `git tag -a "v1.0" c4cdb89s -m "Message here."`   
Delete tag `git tag -d "1.0"`   
List existing tags `git tag`    
Push tag `git push origin 1.0`  
Push all tags `git push --tags origin master`  

Remove a tag `git tag -d release01`  
Push removed tag `git push origin :refs/tags/release01`  

#### Branches

Create a new branch `git checkout -b your_branch_name`  
Push a branch `git push origin your_branch_name`  
See all branches created `git branch`  
Switch to local branch (when is already visible in `git branch`) git checkout your_branch_name  
Switch to remote branch (when is not visible in `git branch`) git checkout -b [branch] [remotename]/[branch]  
Clone a specific `branch git clone git@github.com:nonoesp/laravel-authenticate.git --branch 5.2`  
Remove a branch locally `git branch -d your_branch_name`  
Remove a branch remotely `git branch -dr origin/your_branch_name`  
Remove the branch on git `git push origin :your_branch_name`  
[More on branches](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)  

#### Submodules

Add a submodule w/o path `git submodule add https://github.com/nonoesp/thinker`  
Add a submodule w/ path `git submodule add https://github.com/nonoesp/thinker relative/path/for/submodule`  

#### Downloads

* [WIN](https://git-scm.com/download/win)


## Terminal

Notes on git and terminal commands.

`alias desktop='cd /Users/nono/Desktop'` Create an alias or shortcut for a command on the terminal  


## git-ftp

With git-ftp, you can push our commit to an ftp server and git-ftp will only upload the files that have been changed. It is not what Git is intended for, but in a lot of cases it is a really comfortable use.

`$ git ftp push -u USERNAME -p PASSWORD ftp.server.com/path/to/upload` push your current added and committed changed files to the ftp server

### Install
To have the correct version on OS X, we can install git-ftp with homebrew as follows:

```
brew tap homebrew/dupes
brew install grep
```

### Change Repository Name

First of all, change the name of the repository on the website you are using—Github or Bitbucket for instance. Then change the repository's remote origin with the following code:

```
git remote set-url origin {new-repository-url}
```

### Ignoring files with .git-ftp-ignore

As we can do in Git to ignore files and filetypes, git-ftp allows us to define what to ignore when pushing things to an ftp server. This file does not have any influence in our .gitignore behavior.

### Activate Authentication Keychain Storage on OS X

First, run the following command to make sure the git-credential-osxkeychain program is installed and working in your computer.

	chmod a+x git-credential-osxkeychain

Then, run the following command—which will store your username and password inside your OS X keychain the next time you log in.

	git config --global credential.helper osxkeychain

## License

Notes-Git is licensed under the MIT license. (http://opensource.org/licenses/MIT)

## Me

I'm [Nono Martínez Alonso](http://nono.ma) (nono.ma), a computational designer with a penchant for design, code, and simplicity. I tweet at [@nonoesp](http://www.twitter.com/nonoesp) and write at [Getting Simple](http://gettingsimple.com/). If you use this package, I would love to hear about it. Thanks!
