<h1 align="center">
Git and Github for Beginners
</h1>
<p align="center">by Gwen Faraday and freeCodeCamp</p>

## Table of Contents
1. [Git Commands](#git-commands)
2. [SSH Keys](#ssh-keys)
3. [Git Brancing](#git-branching)

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

## Git Branching

1. 