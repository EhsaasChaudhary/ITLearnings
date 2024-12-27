# Git / Github Commands

## **Git Init and Git Status**

### **`git init`**
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
- `-b <branch-name>`: Creates the repository with an initial branch named `<branch-name>` instead of the default `main` branch.
  ```bash
  git init -b <branch-name>
  ```

### **`git status`**
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
