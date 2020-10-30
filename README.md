# git-commands
Useful list of git commands

## Clone a repository

How to clone a repo creating the folder with a different name (eg: git_commands)

```bash
git clone https://github.com/fraigo/git-commands.git git_commands
cd git_commands
```

To clone a single branch from a repository (useful only  when the repository is very large and contains binary files that slow down the performance of the repository) [Since Git 1.7.10]

```
git clone --single-branch --branch my-branch https://github.com/fraigo/git-commands.git
```

## Cleaning a repository

Discard all changes to modified files in your repo. Only staged files (exclude untracked files)

```
git reset --hard HEAD
```

Discard all untracked files (You can check first which files would be removed with git clean -n)

```
git clean -f
```

Unstage all files (remove after running git add) or, optionally, some specific file(s) adding -- path/to/file

```
git reset [-- path/to/file]
```

Revert the last commit (locally, before pushing to remote). This will remove the last commit. All committed files will be returned to stage (pre-commit). You can use it, again and again, to go back one step more.

```
git reset --soft HEAD~1
```

## Pushing

How to push local to the remote (master) repository for the first time (to an empty repo)

```
git remote add origin https://github.com/fraigo/git-commands.git
git push -u origin master
```

## Refactoring

Reset your repo to a previous commit (all changes after this commit will be removed). You can see the commit hashes using git log

```
git reset --hard e8fe18df3a8ff8220b9158f53a37dc163f45bc67
```

Forcing a remote repo to match the local repo (also for branches)

```
git push -force origin master
```

## Branches

List current branches

```
git branch
```

Create a new branch in your local repo and switch to that branch

```
git checkout -b new-branch
```

Also, the first push of a new branch to a remote should be (-u is equivalent to the option --set-upstream ). In this way, you can push and set up to track the remote branch origin/new-branch

```
git push -u origin new-branch
```

Checkout/Switch to an existing branch

```
git checkout test-branch
```

Delete a branch locally and remotely

```
git branch -d my-branch
git push origin --delete my-branch
```

After deleting the branch you can sync (prune) your local branches using

```
git fetch -p
```
