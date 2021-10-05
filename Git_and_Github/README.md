<h1 align="center">
Git and Github for Beginners
</h1>
<p>by Gwen Faraday and freeCodeCamp</p>

## Table of Contents
1. [Git Commands](#git-commands)
2. [SSH Keys](#ssh-keys)

## Git Commands

clone - downloads a repository into your local directory.

```
git clone git
```

add - track files and changes.

commit - save your files.

push - upload commits to a remote repository.

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