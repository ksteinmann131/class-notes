# Git Commands

Remember that when we create a git repository and then clone it on our computer, we are creating the repo on both the remote (github.com) and local (our machine). We can then work on the local, and push/pull it to/from the remote so that both are synced.
___

- git branch : shows what branch you're currently in and all other branches
- git status : shows status of new files in current branch (if things have been committed or not)
___

- git checkout -b (name of branch) : creates new branch and checks it out (goes to it)
- git branch -d 'name of branch' (then follow prompts in terminal) : deletes branch on local
  - have to be in the master branch to do this action
  - be careful with this!  only want to delete a branch on the local if it's already been pushed to the remote
___

- git add -A : adds all changes to commit cue
- git add (name) : adds whatever is named
- git add . : adds current folder/file
___

- git commit -m "something about what you're committing" : commits changes to current branch
___

- git push origin master : pushes commit to master remote
- git push origin (branch name) : pushes commit to branch remote
___

- git pull origin master : pulls master remote to local
- git pull origin (branch name) : pulls branch remote to local
___

- git clone (url) : use to link new github repo and local files
___

- git remote add origin
___

- git checkout.
- git clean -df
- git reset -- hard origin/master
  - BE CAREFUL! these are very destructive
