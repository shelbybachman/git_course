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

