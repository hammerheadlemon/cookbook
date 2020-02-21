# Rebasing advice

I'm working on a forked repo. I've created a new branch and am working on it,
making commits. I want to share the work on my fork so that I can work on
another computer so I am pushing those commits with `git push origin <branch>`.
I want to squash those commits eventually to a single commit that I can use for
the Pull Request.

If you do a basic `git rebase` and your local repo is in order, however you
have now merged from `origin/branch`.

```git
* 155ec9b (HEAD -> 399) added conftest.py and started adding tests
| * 6fb3725 (origin/399) added a test for date validator
| * e89067d renamed file and some refactoring
| * d905d91 added test for valid string and rejecting empty or none
| * 3c94420 starting to test input validation
| * 47afa0a added conftest.py file and first two tests
|/  
* 92fab4d (upstream/master, origin/master, origin/HEAD, master) Ability to override and edit event colour (#397)
```

You can see here that `399` (my topic branch) is only one commit beyond
`master` which is what I wanted but `origin/399` now needs to be merged. There
is actually no need to do that becauase the content of the `origin/399` branch
are already in `155ec9b` here, so we want to get rid of the useless branch.

My solution is to create a new branch on HEAD, push that to remote and then
delete both the local and remote branches of `399`.

```bash
git checkout 399  # ensure we are on the correct branch
git checkout -b 399_fix  # create new branch at head
git push origin 399_fix  # push the new branch to remote
git push --delete origin 399  # delete remote 399 branch
git branch -d 399  # delete local 399 branch
```

## Deleting old remote branch after PR

I wasn't sure what to do with an old branch used for a previous PR in my fork
repo. I had already removed the local branch. This fixed it:

```bash
git push --delete origin <remote_branch>
```

As long as the changes have been merged, git allows you to destroy old branches
like this.

## Lesson

I originally got into a mess with my git branches by pushing a commit to remote
and then going back and doing a `git --amend`, adding a new change I'd
forgotted into that that commit, leaving me with a divergence from the local
branch and the remote. I didn't want to merge commit and mess up the history,
so I ended up doing `git pull` and going down the `git rebase` route.
