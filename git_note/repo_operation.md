## branch operation

```bash
git branch -a # listing all branches
git branch <branch-name> # createing a new branch named <branch-name>
git checkout -b <branch-name> # switch to <branch-name> branch
git checkout -b <branch-name> # create and switch to <branch-name> branch
git branch -d <branch-name> # deleting a branch named <branch-name>
git merge <branch-name> # merging <branch-name> into current working branch
git remote prune <origin> # synchronize remote branch state, deleting stale remote branches
```

## submodule operation

```bash
git clone --recursive <url> # clone git repos's submodule too
git submodule update --init  --recursive # init git submodule
```
