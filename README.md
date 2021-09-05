1. [github cli](#git)
2. [git](#git)

# github with git cli
* since 13th august 2021 login works only with _personal access token_
* generate a token with a given expiration and scopes (repo, workflow): https://github.com/settings/tokens
* you can use the PAT as password when doing a `git push` 
* alternativly you can cache the PAT
```bash
git config --global credential-helper cache
# now open new terminal login with user and PAT
git push

# when the PAT is expired you can force re-login 
git config --global --unset credential-helper
```

# github cli
* get latest github cli release: https://github.com/cli/cli/releases. ex. `wget`, `curl`
* decompress file, create symbolic link, add `bin` path to your `.profile` file.
```
tar xfv gh_1.2.0_linux_amd64.tar.gz
ln -s gh_1.2.0_linux_amd64/ gh
PATH="$HOME/gh/bin:$PATH"
```

## ready
* you can login with `gh auth login`, then web browser (one time code)
```
gh auth status

You are not logged into any GitHub hosts. Run gh auth login to authenticate
```

```
gh repo view leventarican/cookbook
gh api repos/:owner/cookbook/traffic/views
gh api repos/:owner/cookbook/traffic/clones
```

* https://developer.github.com/v3/repos/traffic/

# git

## undo, remove, revert, undoing

undo from staging
* you did ```git add``` and want to undo it?
`git reset <file>`

remove commit
* remove last commit from repository
`git reset --hard HEAD^`
* or last two commit: `git reset --hard HEAD~2`

revert commit
* revert a commit: `git revert commit`

further link
* good overview about undoing in git: https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/

## clone
* `git clone repo.git`    // user and password prompt
* `git clone user@repo.git`   // password prompt
* `git clone user:pass@repo.git`

## branch
* create a branch: `git branch branchname`
* list all branches: `git branch -a`
* switch to branch: `git checkout branchname`
* check that working on branch: `git branch`
* delete a branch: `git branch -d branchname`

merge branch (feature) to master (branch)
* first checkout to master `git checkout master`
* then execute merge command: `git merge feature`

## to github
* first create a repository on github: `git remote add origin https://github.com/leventarican/git.git`
* push to master `git push -u origin master`
* or push to another branch: `git push -u origin branchname`

## list user config
`git config --list`
`git config --l`

## create user config (.gitconfig at home dir)
`git config --global user.name "leventarican"`
`git config --global user.email "leven@protonmail.com"`

## setup git configuration
```
touch ~/.gitconfig
git config --global user.name "leventarican"
git config --global user.email "levent@protonmail.com"
git config --global -l 
```

## log
* one line: `git log --oneline` 

## git alias (ubuntu .profile)
* append this to your .profile
* to apply do: `source .profile`
```
# git add, commit and push: gp this is a comment
gitpush() {
    git add .
    git commit -m "$*"
    git push
}
alias gp=gitpush

gitcommitpush() {
    git commit -m "$*"
    git push
}
alias gcp=gitcommitpush
```
