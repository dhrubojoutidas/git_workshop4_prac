

## 📘 Git Workshop Notes — Developer Workflow & Setup

``` bash


### ✅ Basic Git Setup

# Install Git and verify
git --version

# Configure your identity
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# View current settings
git config -l

```

### ✅ Create and Connect Local Repo to GitHub

```bash
# Go to your project folder  cd ~/project

# Initialize Git
git init

# Add all files
git add .

# Commit changes
git commit -m "Initial commit"

# Add remote GitHub repo
git remote add origin https://github.com/dhrubojoutidas/git_workshop4_prac.git

# Verify remote
git remote -v

# Rename branch if needed
git branch -M main

# Push to GitHub and set upstream
git push -u origin main
```


---

### 🧑‍💻 Two-Developer Simulation

#### (e) Developer 1: Clone and Setup

```bash
cd ~
git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git myproject2
cd myproject2
```

#### (f) Developer 1: Create Branch and Push

```bash
git checkout -b change_symbols
# Edit Maze.py or any file
git add .
git commit -m "Change symbols in text"
git push -u origin change_symbols
```

#### (g) Developer 2: Fetch and Switch

```bash
cd ~
git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git dev_2_project_folder
cd dev_2_project_folder
git fetch origin
git checkout change_symbols
git log --oneline
```

---

### 🛠️ Git Tips & Tools

- View all Git commands: `git help -a`
- Get help for a command: `git help <command>`
- Tab completion: `git co<tab>` → shows available options

---

### 🧹 Handling Python Cache Files

```bash
# Create .gitignore
__pycache__/
*.pyc

# Add and commit
git add .gitignore
git commit -m "Added .gitignore to ignore Python cache files"
```

---

### ⚙️ Line Ending Settings (Windows vs Linux)

```bash
# Set autocrlf for Windows
git config --global core.autocrlf true

# Optional: .gitattributes
* text=auto
```

---

Let me know if you want to add diagrams, links to your actual repo, or Markdown badges. I can also help you push this README to GitHub if you want to test it live.
