# 


git checkout filename - goes back to the last commit for that file. 
any changes made will be gone and there is no way to undo it
```bash
$ git checkout filename
```


To modifiy commit message - this changes git commit hash too. it means it changes git history. this cause problem to other people's git history. 
```bash
$ git commit --amend -m "modified message"
```


Adding staged files to the last git commit. This also changes git commit hash(changes git history)
```bash
$ git commit --amend 
```

When commited to a wrong branch. ex) you were supposed to commit to a feature branch, but accidentally commited to the master branch.

ex) moving a commit made on master to the feature branch

cherry-pick does not delete a commit
```bash
$ git checkout master (go to master first)
$ git log (copy commit hash you want to move)
$ git checkout feature (switch to feature branch)
$ git cherry-pick hash
```



git rest

if you want to go back to commit C, then use commit hash of B

git log
commit A
commit B
commit C
commit D




git reset --soft hash
soft reset us back to the commit we specified, but it keeps our changes that we made wihin staging area. 
```bash
$ git reset --soft hash
$ git log
```

git reset hash (default)
files changed are not in staging area, but it's in working directory
```bash
$ git reset hash
$ git log
```



git reset --hard hash
all of our tracked files match the state that they wre in at the hash we specified. This gets rid of your changes
it reverts all of the tracked files back to the state they were but it leaves any untracked files alone
```bash
$ git reset --hard hash
$ git log
```

get rid of untracked file - this acutally delets untracked files and direcotry
``` bash
git clean -df # -d for directory, -f for files
```


git history

Usually do not change git history if other people have pulled those changes already. 

git revert

It creates a new commit to reverse the effect of some earlier commits so this way you dont rewrite any history. its not going to modify or delete our existing commits that you've made.  it's going to create a new commit on top of the commit you want to delete/modify and it will undo all of the changes so that our histirt renaubs intact.

It does not delete a commit, which is safe in terms of not changing git history.


``` bash

git revert hash
```
