# Hotfix Branches

### Making changes

````bash
# create and switch to a new branch off of master
$ git checkout -b hotfix/fix-something master

# make changes, fix bugs, and bump patch version...

# commit changes
$ git commit -a -m "bump version to v1.2.1"

# now we can finish the hotfix
$ git checkout master

# merge it into master
$ git merge --no-ff hotfix/fix-something

# tag it
$ git tag -a v1.2.1
````

### Sync with `develop`

You'll need to keep `develop` in sync, so we need to merge to `develop` too

**UNLESS a `release` branch exists, the `hotfix` must be merged into the `release` branch instead.**

````
# checkout develop
$ git checkout develop

# merge release into develop
$ git merge --no-ff hotfix/fix-something
````
