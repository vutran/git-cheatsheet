# Release Branches

### Making Changes

````bash
# create and switch to a new branch off of develop
$ git checkout -b release/v1.2.0 develop

# update versions in README's, config files, etc...

# add a release commit
$ git commit -a -m "bumped version to 1.2"
````

### Finishing a `release`

````bash
# check out master branch
$ git checkout master

# merge release into master
$ git merge --no-ff release/v1.2.0

# tag the master
$ git tag -a v1.2.0
````

### Sync with `develop`

You'll need to keep `develop` in sync, so we need to merge to `develop` too

````bash
# checkout develop
$ git checkout develop

# merge release into develop
$ git merge --no-ff release/v1.2.0

````
