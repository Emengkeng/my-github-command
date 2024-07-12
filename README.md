# my-github-command
The github commands i want to remember

# remove remote origin from a Git repository [source https://stackoverflow.com/a/16330439/17302876]
Instead of removing and re-adding, we can do this:

git remote set-url origin git://new.url.here


# how to delete all commit history in github? [source https://stackoverflow.com/a/26000395/17302876 ]
Checkout/create orphan branch (this branch won't show in git branch command):

git checkout --orphan latest_branch
Add all the files to the newly created branch:

git add -A
Commit the changes:

git commit -am "commit message"
Delete main (default) branch (this step is permanent):

git branch -D main
Rename the current branch to main:

git branch -m main
Finally, all changes are completed on your local repository, and force update your remote repository:

git push -f origin main
PS: This will not keep your old commit history around. Now you should only see your new commit in the history of your git repository.


# Git ignore does not ignore some files [https://stackoverflow.com/a/45400404/17302876]

git rm --cached
