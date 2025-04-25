
# 🧭 Ultimate Guide to Create and Upload Repositories with Git and GitHub (Python + WSL)
✅ Objective
Ignore sensitive files like .env

Track requirements.txt with project dependencies

Create the repo from local and upload it clean to GitHub (public or private)

Use the main branch from the start

Compatible with WSL and Python environment

## 📜 Essential Git Commands
```bash
git status              # View changes
git add file.py         # Add specific file
git commit -m "message"
git push                # Upload changes
git pull                # Fetch changes from remote
```

## 🔧 Step by Step: Create a Local Project with Git and Python
1. Create the project directory
```bash
mkdir my-project
cd my-project
```
2. Create and activate a virtual environment
```bash
python3 -m venv venv
source venv/bin/activate
```
3. Install dependencies and generate requirements.txt
```bash
pip install requests beautifulsoup4
pip freeze > requirements.txt
```
4. Create the .gitignore file
```bash
nano .gitignore
```
## 📄 Recommended content:

```gitignore
# Virtual environment
venv/

# Environment variables
.env

# Caches and compiled files
__pycache__/
*.pyc
```

5. Initialize the repository with the main branch
```bash
git init -b main
```

6. Add and commit the files
```bash
git add .
git commit -m "First clean commit with .gitignore and requirements"
```

## ❗ Did you already upload files that are now in .gitignore?
```bash
git rm --cached -r .
git add .
git commit -m "Apply .gitignore and clean ignored files"
```
This does not delete files from the disk, just from Git's tracking.

7. Create and upload the repository to GitHub
If you use GitHub CLI (recommended):
```bash
gh repo create my-project --private --source=. --remote=origin --push
```
## ✅ This creates the repo, links it, and uploads your code.

## 🧠 Useful Tips
Change the default branch to main globally (once):
```bash
git config --global init.defaultBranch main
```

Update requirements.txt after installing new dependencies:
```bash
pip freeze > requirements.txt
```

## 📦 Key files that should be in your repository
- requirements.txt
- Your source code (.py, .ipynb, etc.)
- .md files, documentation, scripts

## 🔒 Files that should NOT be uploaded (and should be in .gitignore)
- .env
- venv/
- .DS_Store, *.log, temporary files

## 🧾 History and Branches
```bash
git log                 # View commit history
git branch              # View local branches
git switch main         # Switch to another branch
```
