# Syncing a Forked Repository from Upstream

This document explains how to keep your fork up-to-date with the original repository (aka upstream).

## 1. Set up remotes

1. Verify remotes:
   - `git remote -v`

2. Add upstream if missing:
   - `git remote add upstream https://github.com/original-owner/repo-name.git`

3. Confirm remotes:
   - `origin`: your fork
   - `upstream`: original repository

## 2. Sync your local main from upstream

1. Fetch upstream updates:
   - `git fetch upstream`

2. Checkout your local main:
   - `git checkout main` (or `master`)

3. Merge upstream main:
   - `git merge upstream/main`

4. Push the synced main to your fork:
   - `git push origin main`

## 3. Rebase alternative (clean history)

1. `git fetch upstream`
2. `git checkout main`
3. `git rebase upstream/main`
4. `git push --force-with-lease origin main`

## 4. Sync feature branches

1. `git checkout feature-branch`
2. `git rebase main`
3. `git push --force-with-lease origin feature-branch`

## 5. Common commands

- `git pull --rebase upstream main` (fetch + rebase)
- `git fetch upstream --prune` (remove deleted branches)
- `git remote set-url upstream <new-url>` (change upstream URL)

## 6. Best practices

- Sync upstream frequently.
- Work in feature branches, not directly on main.
- Rebase before opening PRs for a linear commit history.
- Use `git status` and `git log` to verify each step.
- Resolve merge/rebase conflicts promptly and carefully.
