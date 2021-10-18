<h1 align="center">
Git and Github for Beginners
</h1>
<p align="center">by Gwen Faraday and freeCodeCamp</p>

## Table of Contents
1. [Git Commands](#git-commands)
2. [SSH Keys](#ssh-keys)

## Git Commands

init - initializes empty git repo.
```
git init
```

clone - downloads a repository into your local directory.
```
# Downloads demo-repo from abechoi
git clone git@github.com:abechoi/demo-repo.git
```

status - outputs tracked, untracked, and modified files within .git
```
git status
```

diff - shows changes since last commit.
```
git diff

# Shows changes against the master branch
git diff master
```

log - show all commits
```
git log
```

merge - merges a branch into the current
```
# Merges master branch into current branch
git branch master
```

branch - displays branches.
```
# Displays all branches
git branch

# Deletes main branch
git branch -d main
```
checkout - switches and modifies branches
```
# Creates and switches to a branch named main
git checkout -b main

# Switches back to master branch
git checkout master
```

add - tracks files and changes.
```
# Adds untracked and modiefied files into the .git as tracked
git add .
```

commit - saves your files.
```
git commit -m "added html"
```

remote - used to add a remote repo address within a local local repo.
```
git remote add origin git@github.com:abechoi/demo-repo2.git
```

push - upload commits to a remote repository.
```
 # Autheniticates user's their repo via SSH Key
 # then uploads changes from local to the remote git repo
 git push -u origin main

# no need for -u origin main after the initialization
 git push
```

pull - download changes from remote repository.
```
git pull
```

reset - unstage changes, from tracked to untracked
```
# undo a commit
git reset

# undo changes to 1 change prior to HEAD
git reset HEAD~1

# undo changes to hash id, which can be found using git log
git reset 142687bb54b659c29fb523103e44f682cc4c3747

# completely unstaged and removed
git reset --hard 142687bb54b659c29fb523103e44f682cc4c3747
```

## SSH Keys

1. Generate SSH key and start agent
```
# Generate SSH key
ssh-keygen -t ed25519 -C "abraham.choi@icloud.com"

(accept default prompts)

# Start ssh-agent
eval "$(ssh-agent -s)"
> Agent pid 51906
```

2. Paste into ~/.ssh/config
```
# Create config file if it does not exist
touch ~/.ssh/config

# Copy the lines below into ~/.ssh/config
Host *
  AddKeysToAgent yes
  IdentityFile ~/.ssh/id_ed25519
```

3. Add SSH private key to the ssh-agent
```
ssh-add -K ~/.ssh/id_ed25519
```

4. Copy and paste id_ed25519.pub into Github
```
# Copies id_ed25519.pub
pbcopy < ~/.ssh/id_ed25519.pub

# Then in Github, go to Settings > SSH and GPG Keys > New SSH Key, and paste
```