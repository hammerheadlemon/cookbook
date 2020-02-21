Ensure we have upstream:
`git remote add upstream <URL>.git`

Fetch all branches of remote into remote-tracking branches, such as
upstream/master
`git fetch upstream`

Make sure that you're on master branch
`git checkout master`

Rewrite your master branch so that any commits of yours that
aren't already in upstream/master are replayed on top of that
other branch:
`git rebase upstream/master`
Instead of the rebase command, i used the following: git merge --no-ff upstream/master This way your commits aren't on top anymore
https://stackoverflow.com/questions/7244321/how-do-i-update-a-github-forked-repository
