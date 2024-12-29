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

