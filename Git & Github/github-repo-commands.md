# Step-by-Step Guide to Push Files to a Remote Git Repository

## Optional Steps

- If you haven't configured your Git username and email, use the following commands before committing:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

## 1. Initialize a Git Repository
```bash
git init
```
This command initializes a new Git repository in the current directory.

## 2. Add Files to the Repository
```bash
git add .
```
This command stages all the files in your directory for a commit.

## 3. Commit the Files
```bash
git commit -m "Initial commit"
```
This command commits your staged files with a message describing the changes.

## 4. Add the Remote Repository
```bash
git remote add origin git@github.com:EhsaasChaudhary/dfdf.git
```
This links your local repository to a remote repository hosted on GitHub.

### Options for `git remote`
- `git remote -v`: Lists the remotes and their URLs.
  ```bash
  git remote -v
  ```
- `git remote rename <old-name> <new-name>`: Renames a remote.
  ```bash
  git remote rename origin upstream
  ```
- `git remote remove <name>`: Removes a remote.
  ```bash
  git remote remove origin
  ```

---

## 5. Rename the Default Branch
```bash
git branch -M main
```
This command renames the default branch to `main`.

### Options for `git branch`
- `git branch -a`: Lists all branches, including remote branches.
  ```bash
  git branch -a
  ```
- `git branch -d <branch>`: Deletes a local branch.
  ```bash
  git branch -d feature-branch
  ```
- `git branch --set-upstream-to=<remote>/<branch>`: Sets upstream tracking for a branch.
  ```bash
  git branch --set-upstream-to=origin/main
  ```

---

## 6. Push the Code to the Remote Repository
```bash
git push -u origin main
```
This command pushes the changes in your local `main` branch to the `main` branch of the remote repository and sets the remote as the default upstream.

### Options for `git push`
- `-f`: Forces the push, overwriting changes.
  ```bash
  git push -f
  ```
- `--tags`: Pushes all tags to the remote repository.
  ```bash
  git push --tags
  ```
- `--delete <remote>/<branch>`: Deletes a branch on the remote repository.
  ```bash
  git push origin --delete feature-branch
  ```
---

## 7. Git Tags

Tags are used in Git to mark specific points in a repository's history, often used to indicate release versions (e.g., `v1.0`, `v2.1`). Tags are immutable references to commits.

### Types of Tags

1. **Lightweight Tags**: These are simple pointers to a commit, without any additional metadata.
   ```bash
   git tag <tagname>
   ```
   Example:
   ```bash
   git tag v1.0
   ```

2. **Annotated Tags**: These are stored as full objects in the Git database and include metadata like the tagger's name, email, and date. Annotated tags are recommended for public releases.
   ```bash
   git tag -a <tagname> -m "Tag message"
   ```
   Example:
   ```bash
   git tag -a v1.0 -m "Initial release"
   ```

### Listing Tags
To see all tags in the repository:
```bash
git tag
```

### Deleting Tags
To delete a tag locally:
```bash
git tag -d <tagname>
```

To delete a tag remotely:
```bash
git push origin --delete <tagname>
```

### Pushing Tags to a Remote Repository
To push a single tag:
```bash
git push origin <tagname>
```

To push all tags:
```bash
git push origin --tags
```

### Checking Out a Tag
While tags cannot be directly modified, you can check out a tag to view its associated commit:
```bash
git checkout <tagname>
```
---

## 8. Git Show

The `git show` command is used to display detailed information about Git objects such as commits, tags, or trees. It is commonly used to inspect the details of a specific commit.

### Syntax
```bash
git show <object>
```

### Use Cases
1. **Viewing a Commit**: Displays details of a commit including the author, date, commit message, and changes made.
   ```bash
   git show <commit-hash>
   ```

2. **Viewing a Tag**: Shows information about a specific tag, including its metadata and associated commit.
   ```bash
   git show <tagname>
   ```

3. **Viewing a File at a Specific Commit**: Outputs the content of a file as it existed in a given commit.
   ```bash
   git show <commit-hash>:<filepath>
   ```

### Options
- `--name-only`: Shows only the names of changed files in a commit.
  ```bash
  git show --name-only <commit-hash>
  ```

- `--name-status`: Displays the names of changed files along with their status (added, modified, deleted).
  ```bash
  git show --name-status <commit-hash>
  ```

- `--pretty`: Formats the output. For example:
  ```bash
  git show --pretty=oneline <commit-hash>
  ```

- `--stat`: Shows a summary of changes including file names, insertions, and deletions.
  ```bash
  git show --stat <commit-hash>
  ```

### Examples
- Show the latest commit:
  ```bash
  git show
  ```

- Show details of a specific commit:
  ```bash
  git show 4f2e5a7
  ```

- Show a specific file from a commit:
  ```bash
  git show 4f2e5a7:src/main.java
  ```

### Notes
The `git show` command is a powerful tool for inspecting repository history and understanding changes. It combines commit and diff information for a holistic view of the repository state.

---

## 9. Git Switch

The `git switch` command is a modern replacement for branch-related operations previously handled by `git checkout`. It simplifies switching branches and creating new branches.

### Syntax
```bash
git switch [options] <branch-name>
```

### Common Use Cases
1. **Switching to an Existing Branch**:
   ```bash
   git switch <branch-name>
   ```
   Example:
   ```bash
   git switch main
   ```

2. **Creating and Switching to a New Branch**:
   ```bash
   git switch -c <new-branch-name>
   ```
   Example:
   ```bash
   git switch -c feature/login-module
   ```

3. **Switching to a Remote-Tracking Branch**:
   ```bash
   git switch --track <remote-branch>
   ```
   Example:
   ```bash
   git switch --track origin/feature-xyz
   ```

### Options
- `-c`: Creates a new branch and switches to it.
- `--create`: Synonym for `-c`.
- `--track`: Creates a new branch to track a remote branch.
- `--detach`: Switches to a branch in a detached HEAD state.
- `--discard-changes`: Discards local changes when switching branches (use with caution).

### Examples
- Switch to the `development` branch:
  ```bash
  git switch development
  ```

- Create and switch to a new branch named `feature-api`:
  ```bash
  git switch -c feature-api
  ```

- Switch to a remote-tracking branch:
  ```bash
  git switch --track origin/bugfix-123
  ```

- Switch to a branch in detached HEAD state:
  ```bash
  git switch --detach feature-old
  ```

### Notes
- `git switch` is available in Git 2.23 and later.
- Unlike `git checkout`, `git switch` focuses exclusively on branch-related operations, making it less error-prone.
- Use `git switch` instead of `git checkout` when working with branches for clearer intent.

---

## 10. Git Restore

The `git restore` command is used to restore files or revert changes in the working directory and staging area. It was introduced in Git 2.23 as part of the effort to separate the functionality of `git checkout` into more focused commands.

### Syntax
```bash
git restore [options] <file-path>
```

### Common Use Cases
1. **Restore a File to Its Last Committed State**:
   ```bash
   git restore <file-path>
   ```
   Example:
   ```bash
   git restore README.md
   ```

2. **Unstage a File**:
   ```bash
   git restore --staged <file-path>
   ```
   Example:
   ```bash
   git restore --staged index.html
   ```

3. **Restore All Files in the Repository**:
   ```bash
   git restore .
   ```

4. **Discard Changes Completely**:
   ```bash
   git restore --source=HEAD <file-path>
   ```
   Example:
   ```bash
   git restore --source=HEAD config.yaml
   ```

### Options
- `--staged`: Unstages a file from the index (staging area) without changing the working directory.
- `--source=<commit>`: Specifies the commit to restore from (default is `HEAD`).
- `--worktree`: Restores changes in the working directory (default behavior).
- `--`: Separates file paths from options, avoiding ambiguity.
- `--patch` or `-p`: Allows interactive restoration of parts of a file.

### Examples
- Restore a single file to its committed state:
  ```bash
  git restore app.js
  ```

- Unstage a file:
  ```bash
  git restore --staged app.js
  ```

- Discard all local changes:
  ```bash
  git restore .
  ```

- Interactively restore hunks in a file:
  ```bash
  git restore -p app.js
  ```

### Notes
- `git restore` is available in Git 2.23 and later.
- Use this command instead of `git checkout` for file-specific operations for better clarity.
- Be cautious when discarding changes as they cannot be recovered unless committed.

---

## 11. Git Merge

The `git merge` command is used to combine the changes from one branch into the current branch. It is a key tool for integrating work in Git, often used in collaborative workflows.

### Syntax
```bash
git merge [options] <branch>
```

### Common Use Cases
1. **Merge a Branch into the Current Branch**:
   ```bash
   git merge <branch-name>
   ```
   Example:
   ```bash
   git merge feature-branch
   ```

2. **Merge with a Commit Message**:
   ```bash
   git merge -m "Merge message" <branch-name>
   ```
   Example:
   ```bash
   git merge -m "Merging feature into main" feature-branch
   ```

3. **Abort a Merge**:
   ```bash
   git merge --abort
   ```
   Use this if there are conflicts you do not want to resolve.

### Options
- `--no-ff`: Creates a merge commit even if a fast-forward merge is possible.
  ```bash
  git merge --no-ff <branch>
  ```

- `--squash`: Combines all changes into a single commit.
  ```bash
  git merge --squash <branch>
  ```

- `--abort`: Cancels the merge process.
  ```bash
  git merge --abort
  ```

- `--commit`: Completes the merge with a merge commit.

- `-m <message>`: Adds a custom message to the merge commit.

- `--strategy=<strategy>`: Specifies a merge strategy (e.g., `recursive`, `ours`, `theirs`).
  ```bash
  git merge --strategy=recursive <branch>
  ```

### Examples
- Merge `development` into `main`:
  ```bash
  git merge development
  ```

- Merge with a commit message:
  ```bash
  git merge -m "Merging hotfix" hotfix-branch
  ```

- Perform a squash merge:
  ```bash
  git merge --squash feature-enhancement
  ```

- Abort an ongoing merge:
  ```bash
  git merge --abort
  ```

### Notes
- Resolve conflicts manually if they arise during a merge. Use `git status` to see the conflicting files.
- After resolving conflicts, complete the merge using:
  ```bash
  git commit
  ```
- Avoid merging too frequently without testing to maintain repository stability.

---

## 12. Git Rebase

The `git rebase` command is used to reapply commits from one branch onto another, effectively rewriting the commit history. It is commonly used to maintain a linear project history and integrate changes more cleanly.

### Syntax
```bash
git rebase [options] <upstream>
```

### Common Use Cases
1. **Rebase the Current Branch onto Another Branch**:
   ```bash
   git rebase <branch>
   ```
   Example:
   ```bash
   git rebase main
   ```

2. **Interactive Rebase to Edit Commit History**:
   ```bash
   git rebase -i <commit>
   ```
   Example:
   ```bash
   git rebase -i HEAD~3
   ```
   This opens an editor where you can modify, reorder, or squash commits.

3. **Continue a Stopped Rebase**:
   ```bash
   git rebase --continue
   ```
   Use this after resolving conflicts during a rebase.

4. **Abort a Rebase**:
   ```bash
   git rebase --abort
   ```
   This restores the branch to its original state before the rebase started.

### Options
- `-i` or `--interactive`: Starts an interactive rebase session, allowing you to edit the commit history.
  ```bash
  git rebase -i <commit>
  ```

- `--onto <new-base>`: Rebases the branch onto a different base.
  ```bash
  git rebase --onto <new-base> <upstream> <branch>
  ```
  Example:
  ```bash
  git rebase --onto main feature-branch-old feature-branch-new
  ```

- `--continue`: Continues the rebase after conflicts are resolved.

- `--skip`: Skips the current conflicting commit and proceeds with the rebase.
  ```bash
  git rebase --skip
  ```

- `--abort`: Aborts the rebase and restores the branch to its original state.

- `--preserve-merges`: Preserves merge commits during a rebase.
  ```bash
  git rebase --preserve-merges main
  ```

- `--no-ff`: Ensures that no fast-forward merges are performed during the rebase.

### Examples
- Rebase the current branch onto `development`:
  ```bash
  git rebase development
  ```

- Start an interactive rebase to modify the last 5 commits:
  ```bash
  git rebase -i HEAD~5
  ```

- Rebase `feature-branch` onto `main`:
  ```bash
  git rebase --onto main development feature-branch
  ```

- Skip a conflicting commit during a rebase:
  ```bash
  git rebase --skip
  ```

- Abort a rebase and undo all changes:
  ```bash
  git rebase --abort
  ```

  ### Notes
- Use `git rebase` with caution when working on shared branches as it rewrites commit history.
- To avoid conflicts, ensure your branch is up to date with the target branch before rebasing:
  ```bash
  git fetch origin
  git rebase origin/main
  ```
- After rebasing, force-push the changes to the remote repository:
  ```bash
  git push --force
  ```
---

## 13. Git Stash

The `git stash` command temporarily shelves changes in your working directory so you can work on something else without committing the changes.

### Syntax
```bash
git stash [options]
```

### Common Use Cases
1. **Save Changes**:
   ```bash
   git stash
   ```
   Temporarily saves all changes in the working directory.

2. **List Stashes**:
   ```bash
   git stash list
   ```
   Displays a list of all saved stashes.

3. **Apply Stashed Changes**:
   ```bash
   git stash apply
   ```
   Reapplies the most recent stash to your working directory.

4. **Apply and Drop Stash**:
   ```bash
   git stash pop
   ```
   Reapplies the most recent stash and removes it from the stash list.

5. **Drop a Specific Stash**:
   ```bash
   git stash drop stash@{index}
   ```
   Removes a specific stash from the list.

6. **Clear All Stashes**:
   ```bash
   git stash clear
   ```
   Deletes all saved stashes.

### Options
- `--keep-index`: Stashes only the changes in the working directory, preserving the staged changes.
  ```bash
  git stash --keep-index
  ```

- `--include-untracked`: Includes untracked files in the stash.
  ```bash
  git stash --include-untracked
  ```

- `--all`: Includes all files (tracked, untracked, and ignored) in the stash.
  ```bash
  git stash --all
  ```

- `list`: Displays all stashed changes.

- `pop`: Applies the stash and removes it from the stash list.

- `apply`: Reapplies the stash without removing it from the stash list.

- `drop`: Deletes a specific stash by its index.

### Examples
- Save changes and include untracked files:
  ```bash
  git stash --include-untracked
  ```

- Reapply the most recent stash:
  ```bash
  git stash apply
  ```

- Remove all stashes:
  ```bash
  git stash clear
  ```

- View all stashed changes:
  ```bash
  git stash list
  ```

- Apply and remove the most recent stash:
  ```bash
  git stash pop
  ```

- Drop a specific stash:
  ```bash
  git stash drop stash@{1}
  ```

### Notes
- Stashing is useful when you want to switch branches without committing your changes.
- You can stash specific files using:
  ```bash
  git stash push -m "message" <file>
  ```
- Use `git stash show` to view the changes in a stash:
  ```bash
  git stash show -p stash@{0}
  ```
---

