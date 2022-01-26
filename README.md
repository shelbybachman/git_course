### initialize a local repository

```
# create and enter local directory
mkdir my_repo
cd my_repo

# initialize git repository
git init

# create, add and commit a file
touch README.md
git add README.md
git commit -m 'initial commit'
```

### add remote repository

```
# add remote
git remote add origin <url>

# verify new remote
git remote -v

# create main branch
git branch -M main

# push local commits to remote
# (-u sets up tracking relationship between local and remote)
git push -u origin main
```

### git IDs and references

```
# show full history
git log

# show history with shortened versions of IDs
git log --oneline

# show history with graph
git log --oneline --graph

# show specific git object
# (can use first 4 chars of ID, if unique, or reference)
git show object_ID_or_reference

# show current commit
git show HEAD

# show current commit's parent
git show HEAD~

# short current commit's parent's parent
git show HEAD~~
```

### git tags

```
# view tags in repository
git tag

# permanently attach a tag of v0.1 to the last commit
git tag -a -m "tag_message" v0.1

# show commits with tag of interest
git show v0.1

# push tag to remote repository
git push origin v0.1

```

### branches

```
# view branches in repository
git branch

# create new branch
git branch branch_name

# switch to new branch
# and update working tree with files from checked out branch
git checkout branch_name

# delete a branch
git branch -d branch_name

# delete a branch if not fully merged
git branch -D branch_name

```

### merges

```
# fast-forward merge: moves base branch label to tip of topic branch
git checkout main
git merge branch_name
git branch -d branch_name

# (a merge is fast-forwardable if no commits have been made to base branch since branching)

# merge with a merge commit
git merge --no-ff branch_name
```

### merge conflicts

```
# checkout base branch
git checkout main

# try to merge feature branch with main branch
git merge featureX

# once prompted with a merge conflict,
# fix file(s) causing the conflict
git status

# stage fixed file(s)
git add fileA.txt

# commit merge conflict
git commit -m 'fix merge conflict due to featureA.txt'

# delete merged feature branch
git branch -d featureX

# (also: abort merge attempt)
git merge --abort
```

### tracking branches

```
# view local and tracking branches
git branch --all

# change default remote tracking branch
# (usually <remote> is origin)
# (can also change default branch for all users in github)
git remote set-head <remote> <branch> 

# view combined log of local and tracking branches
git log --all --oneline --graph
```

### fetch, push and pull

```
# fetch retrieves new objects and references, updates tracking branches
# without having to merge them into your current work
git fetch
# then pull so long as you can fast-forward merge

# pull combines fetch and merge
git pull  # (default --ff: fast-forward merge)
          # (use --no-ff to include a merge commit)

# push adds commits to remote repository
git push # (-u: set upstream, specify remote branch)
git push -u <repo> <branch>
```

### rebasing

```
# (rebase moves commits to a new base)

# method 1 - change parent of currently checked-out branch
git checkout featureX
git rebase main

# method 2 - change parent, without checking out the branch
git rebase main featureX

# if a conflict arises when trying to rebase,
# fix the file(s), add to staging area, and rebase

# return to pre-rebase state
git rebase --abort

```

### rewriting history
```
# amend most recent commit
git commit -m 'commit_message'
git commit --amend -m 'amended_commit_message'

# interactive rebase
# (also use to delete a commit)
git rebase -i <after_this_commit>

# squash a commit
# (combines most recent into a previous commit)
git rebase -i <after_this_commit>

# squash merge
# (merges tip of feature branch onto tip of base branch)
git checkout main
git merge --squash featureX
git commit  # create squash merge commit
git branch -D featureX
```

### pull requests

```
# single repo pull request:

git branch featureX
git checkout featureX
# (do work on the branch)
git push -u origin featureX
# (manage pull request on github)

# multi-repo pull request:

# (fork upstream repo)
# create branch on fork
# create pull request from fork
