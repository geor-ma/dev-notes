# Git Notes

### Notes
- can do git init on folder with already existing files/code
- [Visualizing Git](https://git-school.github.io/visualizing-git/)
- Staging area and index are same - available in .git/index

### Useful Commands


### git on mac

```bash
brew install git
```

### git help
```bash
man git
git help
git help config
```

### config

```bash
git config --list

git config user.name

# global config
git config --global user.name "user name"
git config --global user.email "user@name.com"

# local folder config
git config  user.name "user name"
git config user.email "user@name.com"
```

### git initialization and setup remote

```bash
git init
git add README.md
git commit -m "commit message"

# setup remote origin
git remote add origin https://github.com/repositoryname....

# push to origin
git push -u origin main

# then on, use 
git push
```


### amend - make changes to current commit

```bash
# best practice is not to change history once pushed to shared repo (remote repo) as someone 
# could have got the latest. this messes up others history
#
git commit --amend

```

### Diff

```bash
git diff --staged

# compare working area to index/staging
git diff

# compare index/staging with repository
git diff --cached

# compare commits
git diff HEAD HEAD~2

# compare branches
git diff branch1 branch2

```

### Discard changes from working directory

```bash
git checkout -- <file>
```


### Status

```bash
git status --short
```


### Git add, commit

```bash
#add to staging area
git add <file>

# add and commit files in one command (-a) with (-m) message
git commit -am "commit message here"
```

### Log

```bash
git log -2
git log --oneline
git log --graph --decorate --oneline

# more detail
git log --stat
git log --patch

git log <SHA1>
git log HEAD~5..HEAD^ --oneline

# branch comparison of commits
git log branch1..main --oneline

git help log

git log --grep apples --oneline

git help grep
```

### Get commit information

```bash
git blame <file name>

# show
git show <commit sha1>/<branch>/HEAD

# show parent commit of HEAD
git show HEAD^

# show parent of parent commit of head
git show HEAD^^ or git show HEAD~2

# HEAD~2 = go to head and then to the 2nd commit from the HEAD (ie 3rd commit from head)
git show HEAD~2

# show details of commit - go to head and then the 2nd commit from the HEAD, then pick 2nd parent
git show HEAD~2^2

git show HEAD@{"1 month ago"}
```

### show content of a git file

```bash
git cat-file <commit hash>
git cat-file -p <commit hash>
```

### Remove/untrack file from git

```bash
git rm <file name>

# untrack file
git rm --cached <file name>
# OR
git reset HEAD <file>

# rename a file in git
git mv <file> <file>
```

### Stash

```bash
git stash
git stash list
git stash show

# pops to working directory
git stash pop 
```

### reset

> reset moves the current branch to a commit.

> ref/credit: https://stackoverflow.com/questions/2530060/in-plain-english-what-does-git-reset-do

```bash

# --soft does not change index or working folder. all the changes show up as changes to be committed with git status. Use this when you realize you've made some bad commits, but the work's all good - all you need to do is recommit it differently.
git reset --soft <commit sha1>

# copies files from repo to index for a selected commit. Leaves working directory as it is.
# mixed is the default option
git reset <commit sha1> or git reset --mixed <commit sha1>

# resets working area and staging/index with files from the git repository with selected commit
git reset --hard <commit>

# reset working and staging/index with all files from repo
git reset --hard HEAD

# reset local repo/working/staging with remote HEAD
git reset --hard origin/<branch name>

# Unstage a file from staging area. --mixed is default
git reset HEAD <file> 
```

### restore

> restore command to unstage (copy file from repo to index only). similar to git reset --mixed <commit>
  
```bash
git restore --staged <file>
  ```

### revert

- reverse of a commit. then, it does a new commit the changes. resolve conflicts if any
- all commit history maintained. 
- It can only change changes. It cannot revert structural changes like merge
- [Reference](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)
  
```bash
git revert <commit sha1 to revert>
  
# check
git log --graph --oneline --decorate
```

### Interactive rebases
  
> use to edit/refactor the history of commits from origin/master before publishing to remote. It is better to use only on local unpublished commits
  
```bash
git rebase -i origin/master
```


### Reference Logs on local folder, branches, commits etc.

```bash
git reflog HEAD 
git reflog refs/heads/master

```
### Remove a large file or password or commits from git history
  
> use filtering tool 'git filter-repo' from (https://github.com/newren/git-filter-repo/)
  
```bash
# keep all files except a file
git filter-repo --path <file-name> --invert-paths
  
# check
git log --oneline
```
  
> entire history is rewritten, all users have to setup/clone again. ***Use as extreme measure***
  
### References

- https://app.pluralsight.com/library/courses/how-git-works/table-of-contents
- https://app.pluralsight.com/library/courses/master-git/table-of-contents
- https://stackoverflow.com/questions/2530060/in-plain-english-what-does-git-reset-do
- https://opensource.com/article/18/6/git-reset-revert-rebase-commands
