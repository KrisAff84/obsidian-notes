# Git Commands

### Git Config Commands

Add this option to apply any git config command globally - *Otherwise the config command will only apply to the current repository*
`--global`

#### Add username and email

```shell
git config user.name <user_name>
git config user.email <user_email>
```

#### Set core editor

```shell
git config core.editor '<editor> --wait'   # 'kiro' or 'code' for editor
```

#### Set a new remote origin URL

```shell
git remote set-url "origin" <new_origin_url>
```

### Rebase Commands

#### Rebase when commits have been made on master and commits have already been made on feature branch

```shell
git checkout master
git pull origin master
git checkout <feature_branch>
git rebase master
```

#### Reset local branch to exactly what is on main/master

*The disadvantage is that it does not preserver the commit history of the feature branch*

```shell
git fetch origin master/main
git checkout <feature_branch>
git reset --hard origin/master
```

#### Squash

```shell
git rebase -i HEAD~n   # n is the number of commits to rebase
```

#### Fast forward feature branch from changes in master

*Unlike the reset command, this will preserve the commit history of both branches*

```shell
git fetch origin master
git merge origin/master   # In feature branch
```

### Stash Commands

#### Create a new stash with a message

```shell
git stash push -m "message"
```

#### View current stashes

```shell
git stash list
```

#### Apply a stash without removing from stash

```shell
git stash apply stash@{<stash_number>}
```

#### Show stash diffs

```shell
git stash show -p stash@{<stash_number>}
```

#### Create a new branch from a stash

```shell
git stash branch <branch_name> stash@{<stash_number>}
```

### Tagging

#### Set initial tag

*Create the repo first, and make sure you are on master/main*

```shell
git tag 0.0.0
git push origin 0.0.0

# Or to push all tags (if more than one)
git push --tags
```

### Fetch Commands

#### Fetch a remote branch and create a local branch from it

```shell
git fetch origin <branch>   # This downloads the branch, but won't automatically create a local branch to track

# You need to run this to create a local branch from the remote branch
git checkout -b <local_branch> origin/<branch>
```

#### List remote branches

```shell
git branch -r
git branch -a   # List remote and local
```
