# Merging a Change from Fork to Main (Upstream)

This document explains how to contribute to an upstream repository using a fork,
and includes best practices for clean, successful pull requests (PRs).

## 1. Create a feature branch in your fork

1. Start from synced main:
   - `git checkout main`
   - `git pull origin main` (or `git pull --rebase upstream main` if upstream remote exists)

2. Create a feature branch:
   - `git checkout -b feature/your-change`

3. Implement your changes.

4. Stage and commit with good commit message:
   - `git add <files>`
   - `git commit -m "feat(module): do thing"`

## 2. Push branch to your fork

- `git push origin feature/your-change`

## 3. Keep branch updated (optional but recommended)

1. Fetch upstream:
   - `git fetch upstream`

2. Rebase feature branch onto upstream/main:
   - `git checkout feature/your-change`
   - `git rebase upstream/main`

3. Push the rebased branch safely:
   - `git push --force-with-lease origin feature/your-change`

## 4. Create Pull Request on GitHub

1. On GitHub, go to your fork and click `Compare & pull request`.
2. Ensure PR target is `original-owner/main` (or the appropriate branch).
3. Provide a descriptive title and detailed body:
   - What changed
   - Why this change is needed
   - How to test
4. Reference related issues: `Closes #123`.

## 5. Participate in review

- Respond to comments promptly.
- Apply requested changes in new commits on the same branch.
- Rebase/squash as requested.

## 6. Merge PR upstream

- If you have write access and maintainers allow, you can merge yourself using `Merge` or `Squash and merge`.
- Otherwise, wait for a maintainer to merge.

## 7. Clean up local and fork branches

1. Delete local branch:
   - `git branch -d feature/your-change`
2. Delete remote fork branch:
   - `git push origin --delete feature/your-change`

## Best Practices

- Work on a feature branch, not `main`.
- Keep commits small and focused.
- Use clear commit messages.
- Rebase periodically to reduce conflicts.
- Run tests and lint before pushing.
- Keep PRs scoped to one issue/feature.
- Use draft PRs if work is in progress.
- Keep upstream synced before final push.
- Use `git status` and `git log` to verify state.
- Avoid forcing changes on shared branches (use `--force-with-lease` when needed).
