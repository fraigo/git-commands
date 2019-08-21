# git-commands
Useful list of git commands

# First-time push local to master repository

```bash
git remote add origin <repo-url>
git push -u origin master
```

## Clone a repository in a local folder

```bash
git clone <repo-url> <folder_name>
cd <folder_name>
```

## Refactor your branch

```bash
git reset --hard <commit-hash>
git push -f origin master
```
