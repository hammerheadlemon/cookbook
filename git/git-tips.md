To remove stuff already in the git repo: git -r --cached <dir>/<file>
git branch -r to list remote branches
git branch -a to list all branches
git branch -v -a : all branches available for checkout
git fetch origin will fetch remote branches, then git checkout -b bullshit origin/bullshit to start a new local branch called bullshit from remote branch origin/bullshit `git remote -v update` or `git remote update`.
Then you can do `git status -uno` will tell you whether your tacking
is ahead, behind or has diverged. If nothing, remote and local are the same.
`git show-branch master` will show you commits in all branches whose names end in master
How to remove files and folders from git history: go to this web page: http://dalibornasevic.com/posts/2-permanently-remove-files-and-folders-from-a-git-repository

To track a remote branch:

	When you clone a repository, it generally automatically creates a master branch that tracks origin/master. However, you can set up other tracking branches if you wish – ones that track branches on other remotes, or don’t track the master branch. The simple case is the example you just saw, running git checkout -b [branch] [remotename]/[branch]. This is a common enough operation that Git provides the --track shorthand:

	$ git checkout --track origin/serverfix
	Branch serverfix set up to track remote branch serverfix from origin.
	Switched to a new branch 'serverfix'

	In fact, this is so common that there’s even a shortcut for that shortcut. If the branch name you’re trying to checkout (a) doesn’t exist and (b) exactly matches a name on only one remote, Git will create a tracking branch for you:

	$ git checkout serverfix
	Branch serverfix set up to track remote branch serverfix from origin.
	Switched to a new branch 'serverfix'


Checkout git checkout - <FILE> to interactively include or exclude unstaged changes from index before staging
