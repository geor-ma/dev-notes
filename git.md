# Git Notes

### Notes
- can do git init on folder with your files/code

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
git diff

# Unstage a file from staging area
git reset HEAD <file>

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
git cat-file .git/..

git rm <file name>

# untrack a file
git rm --cached <file name>

git mv <file> <file>




```
