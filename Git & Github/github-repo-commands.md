# Step-by-Step Guide to Push Files to a Remote Git Repository

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
git remote add origin git@github.com:EhsaasChaudhary/gitrepo.git
```
This links your local repository to a remote repository hosted on GitHub.

## 5. Rename the Default Branch
```bash
git branch -M main
```
This command renames the default branch to `main`.

## 6. Push the Code to the Remote Repository
```bash
git push -u origin main
```
This command pushes the changes in your local `main` branch to the `main` branch of the remote repository and sets the remote as the default upstream.

## Optional Steps

- If you haven't configured your Git username and email, use the following commands before committing:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```
  ---
