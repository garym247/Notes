# Handy Git Tools
* GitKraken
* SourceTree (only available for Windows and MacOS)
* posh-git 
* Git Extensions

# Configuring Git


## Different ways to configure Git

* system all users (see C:\Program Files\Git\etc\gitconfig)
* global       all repos belonging to a user (see C:\Users<username>\.gitconfig)
* user          local repo for user


## Checking if Git is installed
```git --version```

## Checking the current configuration of Git

```git config --list```
```git config --global --list```
```git config --global user.name <name of user>```
```git config --global user.email <user email address>``
```git config --global  core.editor "code --wait" ```
* sets VS Code as Git’s default editor


```git config --global -e```



* allows the user edit the global configuration settings via the Git’s default editor


```git config --global autocrlf true```


## Configuring Difference and Merge Tools (run in Command Prompt not Powershell)

### Configure using DiffMerge
```
git config --global diff.tool diffmerge
git config --global difftool.diffmerge.cmd "C:\Program Files\SourceGear\Common\DiffMerge\sgdm.exe \"$LOCAL\" \"$REMOTE\""
git config --global merge.tool diffmerge
git config --global mergetool.diffmerge.trustExitCode true
git config --global mergetool.diffmerge.cmd "C:/Program\ Files/SourceGear/Common/DiffMerge/gdm.exe-merge -result=\"$MERGED\" \"$LOCAL\" \"$BASE\" \"$REMOTE\""
git config --global difftool vscode
git config --global difftool.vs.cmd "code --wait --diff $LOCAL $REMOTE"
```

### Configure using KDiff3
```
git config --global merge.tool kdiff3
git config --global mergetool.kdiff3.path "C:/Program Files/KDiff3/bin/kdiff3.exe"
git config --global mergetool.kdiff3.trustExitCode false

git config --global diff.guitool kdiff3
git config --global difftool.kdiff3.path "C:/Program Files/KDiff3/bin/kdiff3.exe"
git config --
```

# Repos

## Creating a repo from scratch
```git init```

## Cloning an existing repo
```git clone <url>```
* can use this to clone a github repository
* GitHub usually provides a URL for the clone command.


```git clone --progress -v "https://github.com/porridge68/TestRepo.git```

## Querying a repo
```git remote show origin```

```git remote -v```

```git remote get-url origin```
* returns the URL from which the repo was cloned


# Changesets
## CRUDing Staged Files

```git add <file>```
* stages a single file

```git add .```
* stage all files

```git add *.cpp```
* stage all files matching the pattern 

```git rm```
* remove file from working directory and staging area

```git mv```
* rename file  in working directory and staging area

Querying the repo

```git status```

```git ls-files```
* lists the files in the staging area

```git log```


## Committing Staged Files

Each commit contains a complete snapshot of the project


```git commit```
* will open up Git’s default editor to allow the user edit the changeset’s commit message 


```git commit -m "<commit message>"```
* the -m "&lt;commit message>" option is good for doing single line commit messages


```git commit -a```
* will stage and commit all files that are currently tracked

Viewing History

```git log```

```git log --oneline```

## Viewing a committed changeset

```git show``` 

```git show HEAD```

```git show HEAD-1```

```git show HEAD ~1 <filename>```

```git ls-tree HEAD~1```

============

git stash      only tracked files will be stashed.

git stash apply


# Branches


## Creating branches

```git branch <branch name>```
* creates a local branch


## Listing branches
```git branch```
* lists local branches and indicates what the current branch is


```git branch -r```
* lists the remote branches


## Updating branches

```git fetch```

```git fetch origin```

```git pull origin```


## Deleting branches


```git branch -d <branch name>```
* deletes the local branch

Use `-D` option (instead of `-d`) to forcibly delete the local branch, i.e. discarding unpushed commits or current merge state.


## Switching branches

```git checkout &lt;branch name>```     
* merges &lt;branch name> into the current branch


## Merging branches
```git merge <branch name>```
* merges the current branch to &lt;`branch name>`.


```git mergetool <branch name>```



* merges the current branch to &lt;`branch name>` (uses the configured merge tool)

```git mergetool```

```git push origin master```


# Querying the Repo

```git remote show origin```

lists fetch and push repos

remote branches
