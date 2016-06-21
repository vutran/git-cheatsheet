# Feature Branches

````bash
# create and switch to a new branch off of develop
$ git checkout -b feature/my-new-feature develop

# make changes...
# make changes...
# make changes...

# commits on the my-new-feature branch...
git add -v .
git commit -m "new commit on feature branch"

# checks out develop
$ git checkout develop

# merge feature branch into develop
$ git merge --no-ff feature/my-new-feature

# once merged, you can delete the feature branch
$ git branch -d feature/my-new-feature

# push the develop branch to the remote repo
$ git push origin develop
````

# Incremental Fixes on a Feature Branch

Often, you may merge a `feature` branch into `develop` and find some bugs that needs to be fixed. Re-merging over and over will create a dirty commit log filled with merge messages. To keep it clean, revert the merge and then merge again.

````bash
# checks out develop
git checkout develop

# revert last commit (the merge commit)
git revert --hard HEAD^

# merge feature again (assuming your bug has now been fixed on feature)
git merge --no-ff feature/my-new-feature

# force override push
git push -f origin develop
