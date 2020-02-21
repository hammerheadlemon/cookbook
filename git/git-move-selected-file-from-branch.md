Let's say youve worked on a feature branch and made a few commits. You go back to your main
branch and you decide you want to merge some selected changes from the feature branch. The work
you want appears in only a few files. You can actually checkout out those files into our master
branch and commit:

git checkout template/template.py template/__init__.py (make sure you're on your master branch
before doing this)

You will then have the new or amended files in your index. Commit them, then job done.
http://jasonrudolph.com/blog/2009/02/25/git-tip-how-to-merge-specific-files-from-another-branch/
