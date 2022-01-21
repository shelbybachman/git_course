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

