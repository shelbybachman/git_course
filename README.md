## initialize a local repository

# create and enter local diretory
`mkdir my_repo`
`cd my_repo`

# initialize git repository
`git init`

# create, add and commit a file
`touch README.md`
`git add README.md`
`git commit -m 'initial commit'`

## add remote repository

`git remote add origin <url>`

# verify new remote
`git remote -v`

# create main branch
`git 

# move master branch to main
`git branch -m master main`

# push local commits to remote
# (-u sets up tracking relationship between local and remote)
`git push -u origin main`

# ensure local head points to new branch on github
git remote set-head origin main

