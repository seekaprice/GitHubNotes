# GitHubNotes
A quick reference for using GitHub

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
* create a local branch and swith to it
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
