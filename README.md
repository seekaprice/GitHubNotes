# GitHubNotes
A quick reference for using GitHub

## Revert local changes 
from latest commit, but haven't pushed commit yet
```console
git reset --hard HEAD
```
discard any new files or directories that you may have added, 
in case you want to throw those away. 
If you haven't added any, you don't have to run this.
```console
git clean -f
```

pull from repo
```console
git pull
```

#### if commit has been pushed, then you need to get the log and revert
```console
git log
```
this will give you your latest push commit hash key. You will need the hash key to revert
```console
git reset --hard <your commit hash key>
```

## Get remote origin url
```console
git config --get remote.origin.url
```

## List All Remotes
 ```console
 git remote -v
 ```

## Set new RemoteUrl
```
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```
 
## Repo from existing code or from scratch

* create local folder for project and cd into it
* add local source code if necessary
* run command git init to initialize blank local repo
```console
git init
```
* run git add to add files to local repo
```console
git add .
```
* run git commit -m "message" to commit files to local repo
```console
git commit -m "added project files"
```
* if you don't have a git remote repo, create one
* associate your local repo with the remote repo by 
running command, git remote add origin \<url of remote repo\>
```console
git remote add origin https://github.com/seekaprice/BzNews-Database.git
```
* run git remote -v to see associated remote repo
* grab remote repo files and sync them with your local files
run command git pull origin master --allow-unrelated-histories
```console
git pull origin master --allow-unrelated-histories
```
* check to see if we need to fix any merge issues, merge failed conflicts.
Once conflicts are fixed run git add . and git commit -m "message"
* finally run git push to add all the files to remote
```console
git add .
git commit -m "merged conflicts"
```

* set upstream
```console
git push --set-upstream origin master
```
## create a local branch and swith to it
```console
git branch development
git checkout development
```
* add local development branch to remote origin. NOTE: try to keep the remote name
the same as the local name. Only push to remote origin if you intend to share the local 
work else where
```console
git push -u origin development
```
* Do work on development. When feature is done and tested, merge back to master.
* Make sure you are currently in development branch
```console
git checkout development
```
* Merge master to development branch
```console
git merge master
```
* Resolve any conflicts. Then add, commit, and push to development remote if you
have remote development branch. Then checkout master.
```console
git checkout master
```
* Merge development with master. There should be no conflicts. 
```console
git merge development
```
* Now push local master to remote origin master.
```console
git push
```

* delete remote development branch
```console
git push origin --delete development
```

* delete local development branch. First change back to master.
```console
git checkout master
git branch -d development
```


OTHER GIT COMMANDS to note
add will add a remote origin
set-url will change an existing origin to a different one
```console
git remote set-url origin https://github.com/seekaprice/BzNews-Database.git
git remote add origin https://github.com/seekaprice/BzNews-Database.git
```

multiline git commit message
```console
C:\> git commit -m "Line 1"^
More?
More? "Line 2"^
More?
More? "Line 3"
```

# FORCE Local Overwrite remote

```console
git push origin master --force
```

Git Commands
============

FROM https://raw.githubusercontent.com/joshnh/Git-Commands/master/README.md

_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branchName]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git diff [source branch] [target branch}` | Preview changes before merging |

