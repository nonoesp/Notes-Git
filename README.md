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

#### Log

List commits `git log --pretty=oneline`  

#### Tags

Add tag `git tag -a "v1.0" -m "Message is here, can have line breaks."`  
Add tag to specific commit `git tag -a "v1.0" c4cdb89s -m "Message here."`   
Delete tag `git tag -d "v1.0"`   
List existing tags `git tag`    
Push tag `git push origin v1.0`  

Remove a tag `git tag -d release01`  
Push removed tag `git push origin :refs/tags/release01`  

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

I tweet at [@nonoesp](http://www.twitter.com/nonoesp) and blog at [nono.ma/says](http://nono.ma/says). I would love to hear about it if you find these notes are useful. Thanks!
