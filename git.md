# Git Notes

### Notes
- can do git init on folder with already existing files/code
- [Visualizing Git](https://git-school.github.io/visualizing-git/)
- Staging area and index are same - available in .git/index

### Commands
```bash

# git on mac
brew install git

# help
man git
git help
git help config

# list all config
git config --list

git config user.name

# global config
git config --global user.name "user name"
git config --global user.email "user@name.com"

# local folder config
git config  user.name "user name"
git config user.email "user@name.com"

# git init
git init
git add README.md
git commit -m "commit message"

# setup remote origin
git remote add origin https://github.com/repositoryname....

# push to origin
git push -u origin main

# then on, use 
git push

git diff --staged

# compare working area to index/staging
git diff

# compare index/staging with repository
git diff --cached

# Discard changes from working directory
git checkout -- <file>


git status --short

#add to staging area
git add <file>

# add and commit files in one command (-a) with (-m) message
git commit -am "commit message here"

git log -2
git log --oneline


# more detail
git log --stat
git log --patch

git log <SHA1>

# show content of a git file
git cat-file <commit hash>
git cat-file -p <commit hash>

git rm <file name>

# untrack a file
git rm --cached <file name>
# OR
git reset HEAD <file>

git mv <file> <file>

git stash
git stash list
git stash show

# pops to working directory
git stash pop 

#
# reset moves the current branch to a commit.
# https://stackoverflow.com/questions/2530060/in-plain-english-what-does-git-reset-do
#


# credit - # https://stackoverflow.com/questions/2530060/in-plain-english-what-does-git-reset-do
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

# restore command to unstage (copy file from repo to index only). similar to git reset --mixed <commit>
git restore --staged <file>

# revert

```

### References

- https://app.pluralsight.com/library/courses/how-git-works/table-of-contents
- https://app.pluralsight.com/library/courses/master-git/table-of-contents
- https://stackoverflow.com/questions/2530060/in-plain-english-what-does-git-reset-do
