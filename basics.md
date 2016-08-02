# Basics

### Checkout a new branch

````bash
$ git checkout -b my-new-branch
````

### Checkout a new branch from an existing branch

````bash
$ git checkout -b my-new-branch develop
````

# Pull/Push

Pushes the `master` to a remote repository `origin`

````bash
$ git push origin master
````

Pull changes from the `master` branch in the remote repository `origin``

````bash
$ git pull origin master
````

## Tags

### Tag a branch with a message

````
$ git tag -a v1.4 -m "my version 1.4"
````

### Delete a tag

````
$ git tag -d v1.4
````

### Delete a tag from remote repository

````bash
# delete local tag
$ git tag -d v1.4

# push the deleted tag to the remote repo
$ git push origin :refs/tags/v1.4
````

### Push all local tags to remote

````
$ git push --tags
````
## Rebase

### Rebasing a branch to the latest state of another branch

````bash
$ git rebase target_branch source_branch

# rebase the feature/my-new-branch based on the latest state of develop
$ git rebase develop feature/my-new-feature
````

## Revert/Rollback

Rolls back to a specific commit

````bash
$ git reset --hard {SHA}
````

Reverts a specific commit (creates a new commit with the changed files in the working directory)

````bash
$ git revert {SHA}
````

Reverts the last 3 commits

````bash
$ git revert HEAD~3
````

Revert the last commit

````bash
$ git revert --hard HEAD^
````

## Amend

Amend with edits

````bash
$ git commit --amend
````

Amend with no edits

````bash
$ git comment --amend --no-edit
````

## Miscellaneous

## Unstage all

```bash
git reset HEAD --
```

# Display Last commit

```bash
git log -1 HEAD
```
