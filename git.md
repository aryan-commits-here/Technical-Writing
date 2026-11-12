# Version Control with Git & GitHub

## 1. What is Git and GitHub?

- **Git**: A version control system that runs locally on your computer. It tracks every change you make to files over time so you can view your history, undo mistakes, and work on different features using branches.
- **GitHub**: An online cloud platform that hosts Git repositories. It lets you back up your project online, share code, and collaborate with team members using Pull Requests and issues.

---

## 2. The Basic Git Workflow

When working with Git, changes move through four simple steps:

**Working Directory** $\rightarrow$ `git add` $\rightarrow$ **Staging Area** $\rightarrow$ `git commit` $\rightarrow$ **Local Repository** $\rightarrow$ `git push` $\rightarrow$ **GitHub**

1. **Working Directory**: The actual files you are editing on your computer.
2. **Staging Area**: A list of changes you have selected and prepared to be saved (`git add`).
3. **Local Repository**: The saved history snapshot stored locally on your system (`git commit`).
4. **Remote Repository (GitHub)**: The online backup of your repository where others can view and clone your code (`git push`).

---

## 3. Essential Git Commands

### 1. Setting Up Your Identity
Before making your first commit, set your name and email:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 2. Creating a Repository
```bash
# Initialize a new Git repository in the current folder
git init

# Or download an existing repository from GitHub
git clone https://github.com/username/repository-name.git
```

### 3. Saving Changes
```bash
# Check which files have been modified or are untracked
git status

# Stage a single file
git add filename.md

# Stage all changed files in the folder
git add .

# Save a snapshot of staged changes with a helpful note
git commit -m "feat: add latex basics guide"
```

### 4. Viewing History
```bash
# See recent commit history
git log

# See one-line summary of each commit
git log --oneline
```

### 5. Working with Branches
Branches let you experiment or write new code without breaking the main working code:
```bash
# Create a new branch
git branch new-feature

# Switch to the new branch
git switch new-feature

# Merge the branch back into the main branch
git switch main
git merge new-feature
```

### 6. Syncing with GitHub
```bash
# Connect your local repository to GitHub
git remote add origin https://github.com/username/repository-name.git

# Upload your commits to GitHub
git push -u origin main

# Download the latest changes from GitHub
git pull origin main
```

---

## 4. What is `.gitignore`?

A `.gitignore` file is a simple text file placed in your project root. It tells Git to ignore certain temporary or generated files so they don't clutter your repository.

Common things to ignore:
- Temporary compiler files (`.o`, `.exe`)
- LaTeX auxiliary files (`*.aux`, `*.log`, `*.toc`)
- Doxygen generated folders (`html/`, `latex/`)
- System files (`.DS_Store`, `Thumbs.db`)
