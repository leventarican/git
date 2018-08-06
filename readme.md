# learning tig.

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

## list user config
`git config --list`
