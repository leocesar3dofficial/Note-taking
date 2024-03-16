# Git

## Clone Repository

- Make sure you have Git [installed](#install) and [setup user](#setup)

### Public

```bash
git clone https://github.com/<https name of the project>
```

### Private

1. Generate SSH Key:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

2. Copy the generated SSH Key to GitHub:

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

3. Go to your GitHub account settings, navigate to "SSH and GPG keys," and add your public SSH key.

4. Clone the Repository:

   ```bash
   git clone git@github.com:username/repo-name.git
   ```

## Push an Existing Repository

```bash
git remote add origin git@github.com:leocesar3dofficial/meu-site-dinamico.git
git branch -M main
git push -u origin main
```

## URL of the Repository

```bash
git remote -v
```

## Workflow

### Syntax

```bash
program | action | destination
```

### Status

```bash
git status
```

### Add File to Stage

```bash
git add [file.extension]
git add .  # all files in the current directory
```

### Commit changes to Repository

- Registrar as mudanças locais em um repositório.

```bash
git commit -m "[descriptive message]"
```

- Change commit history (danger of data loss as it overwrites history):

  ```bash
  git commit --amend  # replaces the last commit with current changes
  git rebase --continue
  ```

- Squash commits:

  ```bash
  git rebase -i HEAD~2  # allow to edit the last two commits
  git rebase -i --root  # all the way back to the root commit
  ```

  Git opens a text file (danger of data loss as it overwrites history), change "pick" to "squash."

- Split commits:

  ```bash
  git reset HEAD^
  ```

### Logging

```bash
# full log entry for each commit
git log

# list of commit IDs and their associated commit messages
git log --oneline

# Exibe o histórico de commits de forma concisa e gráfica, incluindo todas as ramificações e tags
git log --oneline --graph --decorate --all
```

### Open Repository in VSCode

```bash
code .
```

### Push to GitHub

```bash
git push  # or git push origin main
git push  # or git push origin <branch_name>
git push -u origin <branch_name>  # force push
git push --force  # force your local project to remote, disregard of project collaborators changes, danger of data loss
git push --force-with-lease  # same as above, but generates an error message if your local repository is not up to date
```

### Revert Changes (Non-Destructive)

```bash
# Undoes the changes to the specified commit
git revert 'commit message'


# Revert the changes to the latest commit
git revert HEAD

# Updates the remote repository with the local changes
git push origin main
```

### Branches

```bash
git branch <branch_name>  # create
git checkout <branch_name>  # change (mudar de repositório)
git checkout -b <branch_name>  # create and change (cria e habilita o branch)
git branch  # list all
git merge <branch_name>  # merge
git fetch upstream  # get updated version of the repository
git branch -d <branch_name>  # delete (already merged)
git branch -D <branch_name>  # delete (not merged yet)
git push --delete origin <branch_name>  # delete (remote)
```

## Install

```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
```

### Version

```bash
git --version
```

### Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "yourname@example.com"
<mailto:yourname@example.com>
```

### Ignore Git Tracking for Files and Folders

- Create the file: `.gitignore`
- Example ignored content:

  ```
  package.json
  node_modules/
  ```

### Colorful Output

```bash
git config --global color.ui auto
```

### Verify User

```bash
git config --get user.name
git config --get user.email
```

## Change Default Branch

```bash
git config --global init.defaultBranch main
```

## SSH Key

### Create SSH Key

```bash
ssh-keygen -t ed25519 -C <youremail>
```

### Check the Existence of the SSH Key

```bash
ls ~/.ssh/id_ed25519.pub
```

### Read the SSH Key File to the Console

```bash
cat ~/.ssh/id_ed25519.pub
```
