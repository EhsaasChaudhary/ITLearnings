# Git / Github Commands

## **Git Init**

The `git init` command initializes a new Git repository in the specified directory. This command creates a `.git` folder that contains all the metadata and history for the repository.

#### **Usage**:
```bash
git init [directory]
```

- If no directory is specified, it initializes the current folder.

#### **Options**:
- `--bare`: Initializes a bare repository that does not have a working directory. Bare repositories are typically used for remote repositories.
  ```bash
  git init --bare
  ```
- `--quiet`: Suppresses the output message.
  ```bash
  git init --quiet
  ```
- `--shared[=permissions]`: Configures repository permissions to be shared among a group. Common values for permissions are `group`, `all`, or `umask`.
  ```bash
  git init --shared=group
  ```
- `--separate-git-dir=<git-dir>`: Creates a Git repository with the `.git` folder stored in a separate directory.
  ```bash
  git init --separate-git-dir=/path/to/git-dir
  ```
- `-b <branch-name>`: Creates the repository with an initial branch named `<branch-name>` instead of the default `main` branch.
  ```bash
  git init -b <branch-name>
  ```

## **Git Status**
The `git status` command displays the state of the working directory and staging area. It shows which changes have been staged, which have not, and which files are not being tracked by Git.

#### **Usage**:
```bash
git status [options]
```

#### **Options**:
- `--short`: Provides a brief summary of the status.
  ```bash
  git status --short
  ```
- `--branch`: Displays information about the current branch.
  ```bash
  git status --branch
  ```
- `--ignored`: Lists the ignored files.
  ```bash
  git status --ignored
  ```

---

## **git add**
The `git add` command adds changes in the working directory to the staging area, preparing them for a commit.

#### **Usage**:
```bash
git add [file-pattern]
```
- To stage all changes:
  ```bash
  git add .
  ```
- To stage a specific file:
  ```bash
  git add <file-name>
  ```

#### **Options**:
- `-n` or `--dry-run`: Shows what files would be added without actually staging them.
  ```bash
  git add -n
  ```
- `-p` or `--patch`: Interactively stages hunks of changes.
  ```bash
  git add -p
  ```

## **git log**
The `git log` command displays the commit history of a repository, showing the sequence of commits.

#### **Usage**:
```bash
git log [options]
```

#### **Options**:
- `--oneline`: Displays each commit on one line for brevity.
  ```bash
  git log --oneline
  ```
- `--graph`: Shows a graphical representation of the branch structure.
  ```bash
  git log --graph
  ```
- `--author=<author>`: Filters commits by a specific author.
  ```bash
  git log --author="Author Name"
  ```
- `--since=<date>` and `--until=<date>`: Filters commits within a date range.
  ```bash
  git log --since="2023-01-01" --until="2023-12-31"
  ```
- `-p`: Shows the differences introduced in each commit.
  ```bash
  git log -p
  ```

## **git commit**
The `git commit` command saves the staged changes to the repository, creating a new commit.

#### **Usage**:
```bash
git commit -m "Commit message"
```

#### **Options**:
- `-m <message>`: Adds a commit message directly.
  ```bash
  git commit -m "Initial commit"
  ```
- `-a`: Automatically stages tracked files before committing.
  ```bash
  git commit -a -m "Updated files"
  ```
- `--amend`: Modifies the most recent commit, including its message.
  ```bash
  git commit --amend -m "Updated commit message"
  ```
- `--no-edit`: Amends the last commit without changing its message.
  ```bash
  git commit --amend --no-edit
  ```

---
