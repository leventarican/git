# learning git.

## undo from staging
* you did ```git add``` and want to undo it?
`git reset <file>`
## remove commit
* remove last commit from repository
`git reset --hard HEAD^`
* or last two commit: `git reset --hard HEAD~2`
## revert commit
* revert a commit: `git revert commit`

## links
* good overview about undoing in git: https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/

## branch
### create a branch
`git branch branchname`

### list all branches
`git branch -a`

### switch to branch
`git checkout branchname`

### check that working on branch
`git branch`

### merge branch to master
* first checkout to master
* then execute merge command: `git merge feature`

### delete a branch
`git branch -d branchname`

## to github
* first create a repository on github, then change user config, then push
`git remote add origin https://github.com/leventarican/git.git`
`git push -u origin master`
`git push -u origin branchname` // to push another branch

## list user config
`git config --list`
`git config --l`

## create user config (.gitconfig at home dir)
`git config --global user.name "leventarican"`
`git config --global user.email "leven@protonmail.com"`

