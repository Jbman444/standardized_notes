# Learning Git

[Git Branching Game](https://learngitbranching.js.org/)


### Git Branching Game

head - where you are currently working
branch - a movable bookmark
commit - a snap shoot


[W3 School](https://www.w3schools.com/git/)


branch is like a label which points to a specific commit (snapshot of your repo)


### Making a new branch and switiching to it

```bash
git switch -c bugfix
```


### commiting to a branch
```bash
# see what has changed in your repo
git status 
# the file you add will be staged (preparing to commit)
git add mod_file 
# if you change your mind you can unstage a file before you commit it
git restore --staged mod_file 
# if you still want to commit 
git commit -m "add a comment"
# before you commit check what branch you are on 
git branch
# check what remote branch you are pushing to 
git remote -v
# after you know the branch you are commiting to go ahead and push
git push origin branch_name
# if it doesn't work you might need to  make a branch and commit that branch or file size is too big ( could be other issues branch management?)

```