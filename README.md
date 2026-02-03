# Learn Git

This repository demonstrates Git basics, intermediate concepts, advanced techniques, best practices, and proper commit message formats.

## Basic Git Commands

These are the fundamental commands to get started with Git.

- `git init`: Initialize a new Git repository in the current directory.
  - **When to use**: Starting a new project or converting an existing directory into a Git repo.
  - **Example**: `git init`

- `git status`: Show the current state of the working directory and staging area.
  - **When to use**: Check which files are modified, staged, or untracked before committing.
  - **Example**: `git status`

- `git add <file>`: Stage changes for the next commit.
  - **When to use**: Prepare specific files or all changes (`git add .`) to be included in the next commit.
  - **Example**: `git add README.md` or `git add .`

- `git commit -m "message"`: Record staged changes in the repository.
  - **When to use**: Save a snapshot of your work with a descriptive message.
  - **Example**: `git commit -m "Add initial documentation"`

- `git log`: Display commit history.
  - **When to use**: Review past commits, authors, and messages.
  - **Example**: `git log --oneline` (compact view)

## Intermediate Git Commands

These commands help manage branches, merges, and collaboration.

- `git branch`: List branches or create a new one.
  - **When to use**: View existing branches or create a new branch for feature development.
  - **Example**: `git branch feature-x` (create) or `git branch` (list)

- `git checkout <branch>`: Switch to a different branch.
  - **When to use**: Work on a different branch or restore files.
  - **Example**: `git checkout feature-x`

- `git merge <branch>`: Merge changes from one branch into the current branch.
  - **When to use**: Combine feature branches back into main branch after completion.
  - **Example**: `git merge feature-x`

- `git pull`: Fetch and merge changes from a remote repository.
  - **When to use**: Update your local repo with changes from collaborators.
  - **Example**: `git pull origin main`

- `git push`: Upload local commits to a remote repository.
  - **When to use**: Share your commits with others.
  - **Example**: `git push origin main`

- `git diff`: Show differences between commits, branches, or working directory.
  - **When to use**: Review changes before committing or merging.
  - **Example**: `git diff` (working vs staged) or `git diff HEAD~1` (vs last commit)

## Advanced Git Commands

These are for complex workflows, history rewriting, and troubleshooting.

- `git rebase <branch>`: Reapply commits on top of another branch.
  - **When to use**: Clean up commit history or integrate changes linearly.
  - **Example**: `git rebase main` (rebase current branch onto main)

- `git reset --soft/--mixed/--hard <commit>`: Reset to a previous commit.
  - **When to use**: Undo commits (soft: keep changes staged, mixed: unstage, hard: discard).
  - **Example**: `git reset --hard HEAD~1` (undo last commit)

- `git cherry-pick <commit>`: Apply a specific commit to current branch.
  - **When to use**: Selectively apply commits from another branch.
  - **Example**: `git cherry-pick abc123`

- `git stash`: Temporarily save uncommitted changes.
  - **When to use**: Switch branches without committing incomplete work.
  - **Example**: `git stash` (save) and `git stash pop` (restore)

- `git bisect`: Binary search through commit history to find bugs.
  - **When to use**: Identify which commit introduced a bug.
  - **Example**: `git bisect start`, then mark good/bad commits.

- `git reflog`: Show reference log of all actions.
  - **When to use**: Recover lost commits or branches.
  - **Example**: `git reflog`

## Best Practices and Patterns

To avoid getting lost in Git:

- **Commit often**: Make small, frequent commits with clear messages.
- **Use branches**: Create feature branches for new work; keep `main`/`master` stable.
- **Pull before pushing**: Always `git pull` to avoid conflicts.
- **Don't rewrite shared history**: Avoid `reset`/`rebase` on pushed commits.
- **Use descriptive branch names**: e.g., `feature/add-login` instead of `branch1`.
- **Review before merging**: Use `git diff` and test changes.
- **Backup important work**: Push to remote or create backups.
- **Learn from mistakes**: Use `reflog` to recover from errors.

Common patterns:
- **Git Flow**: Feature branches → develop → main.
- **Trunk-based**: Frequent merges to main branch.
- **Rebase workflow**: Keep history linear with rebases.

## Proper Commit Message Formats

Good commit messages are clear, concise, and follow conventions.

### Basic Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding tests
- `chore`: Maintenance tasks

### Examples
- `feat(auth): add user login functionality`
- `fix(ui): resolve button alignment issue`
- `docs(readme): update installation instructions`

### Guidelines
- Use imperative mood: "Add" not "Added"
- Keep subject < 50 characters
- Explain what and why, not how
- Reference issues: `Closes #123`

## Forking Workflow

Forking allows you to create a personal copy of someone else's repository on GitHub, enabling you to experiment and contribute without affecting the original project.

### Basic Forking Commands

- **Fork on GitHub**: Click the "Fork" button on the repository's GitHub page to create your copy.
  - **When to use**: Start contributing to open-source projects or experiment with code.
  - **Result**: Creates `https://github.com/yourusername/repo-name`

- `git clone <fork-url>`: Clone your forked repository to your local machine.
  - **When to use**: Work on the forked repo locally.
  - **Example**: `git clone https://github.com/yourusername/repo-name.git`

- `git remote add upstream <original-url>`: Add the original repository as an upstream remote.
  - **When to use**: Keep your fork synced with the original repo.
  - **Example**: `git remote add upstream https://github.com/original/repo-name.git`

### Intermediate Forking Commands

- `git fetch upstream`: Fetch changes from the original repository.
  - **When to use**: Check for updates in the upstream repo.
  - **Example**: `git fetch upstream`

- `git merge upstream/main`: Merge upstream changes into your local branch.
  - **When to use**: Sync your fork with the latest changes from the original repo.
  - **Example**: `git merge upstream/main`

- `git push origin <branch>`: Push your local changes to your fork on GitHub.
  - **When to use**: Upload your work to your GitHub fork.
  - **Example**: `git push origin feature-branch`

- Create a Pull Request (PR): On GitHub, compare your branch with the original repo's main branch.
  - **When to use**: Propose changes to the original project.
  - **Steps**: Go to your fork, click "Compare & pull request"

### Advanced Forking Commands

- `git rebase upstream/main`: Rebase your branch on top of upstream changes.
  - **When to use**: Maintain a linear history when syncing with upstream.
  - **Example**: `git rebase upstream/main`

- `git cherry-pick <commit>`: Apply specific commits from upstream.
  - **When to use**: Selectively incorporate fixes or features.
  - **Example**: `git cherry-pick abc123`

- Managing multiple remotes: Use `git remote -v` to list, `git remote rename` to rename.
  - **When to use**: Organize remotes in complex workflows.
  - **Example**: `git remote rename origin myfork`

- `git push --force-with-lease`: Force push after rebasing (safely).
  - **When to use**: Update your fork after rebasing, avoiding accidental overwrites.
  - **Example**: `git push --force-with-lease origin branch`

### Best Practices for Forking

- **Keep your fork synced**: Regularly fetch and merge/rebase from upstream to avoid conflicts.
- **Use feature branches**: Create branches for each contribution to keep main clean.
- **Don't push to upstream**: Only push to your fork; use PRs for contributions.
- **Rebase before PR**: Rebase your changes on upstream/main for cleaner merges.
- **Delete merged branches**: Clean up after PRs are merged.
- **Understand licensing**: Check the original repo's license before contributing.
- **Communicate**: Use issues and discussions for coordination.
- **Test thoroughly**: Ensure changes work before submitting PRs.

Common pitfalls to avoid:
- Forgetting to sync with upstream, leading to outdated code.
- Pushing directly to upstream (you can't, but don't try).
- Creating PRs from main branch instead of feature branches.