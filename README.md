---

## 🔧 1. Install Git
- 📥 Download Git from [git-scm.com](https://git-scm.com)
- 💻 Install &  Verify installation: git --version

---

## 🧑‍💻 2. Configure Git Identity
Set your name and email (used for commits):
```bash
git config --global user.name "dhrubojoitidas"
git config --global user.email "dhrubotroyee20@gmail.com"
```
Verify:
```bash
git config --global --list
```

---

## 📁 3. Create Project Folder & Initialize Git
```bash
mkdir MazeProject
cd MazeProject
git init
ls -a  # should show: .  ..  .git
```

---

## 🐍 4. Add Maze.py & Make First Commit
Copy `Maze.py` into this folder, then:
```bash
git status
git add Maze.py
git status
git commit -m "Initial commit."
git status
```

> 💡 **What does `git add` do?**  
> It stages your changes — Git marks the file as “ready to be committed”.  
> It does **not** save permanently; it just prepares it for the next commit.

---

## 🌐 5. Connect to GitHub Remote Repo
```bash
git remote add origin https://github.com/dhrubojoutidas/git_workshop4_prac.git
git remote -v
```
---

## 🔀 6. Rename Branch & Push to GitHub
```bash
git branch -M main
git push -u origin main
```

---
 

## 👥 Two-Developer Simulation

### 🧑‍💻 Developer 1: Clone & Create Branch
```bash
cd ~
git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git myproject2
cd myproject2
git checkout -b change_symbols
# Edit Maze.py
git add .
git commit -m "Change symbols in text"
git push -u origin change_symbols
```

---

### 🧑‍💻 Developer 2: Clone, Fetch & Switch
```bash
cd ~
git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git dev_2_project_folder
cd dev_2_project_folder
git fetch origin
git checkout change_symbols
git log --oneline
```

---

## 🧹 Ignore Python Cache Files 

in your project folder Create `.gitignore`  to tell Git to ignore these files::
```
_
			# Python cache
			__pycache__/
			*.pyc
			*.pyo

			# Virtual environments
			venv/
			.env/

			# IDE settings
			.vscode/
    .idea/
```

Then:
```bash
git add .gitignore
git commit -m "Added .gitignore to ignore Python cache files"
```

---


## ⚙️ Line Ending Settings (Windows vs Linux)
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/e097fecb-dcc2-40df-af66-32dd19f12628" />

###  ✅  Windows-friendly (convert LF to CRLF on checkout).
```bash
git config --global core.autocrlf true

```
###  ✅ Linux/macOS-friendly (keep LF, no conversion on checkout).
```bash
git config --global core.autocrlf input

```

 ###  ✅ No conversion at all (you manage line endings manually)
```bash
 git config --global core.autocrlf false
```
 ### 🔧To stop that warning because it tells Git to automatically handle line endings for Windows:
-  When you add files: Git converts CRLF → LF internally.
-  When you checkout files: Git converts LF → CRLF for Windows

Then:
```bash
Continue your workflow:
		○ Add files: git add Maze.py
		○ Commit: git commit -m "Initial commit"
```
---


### ✅ Use this if you want to fix **all previously added files**:

- `git rm --cached -r .` removes all files from the staging area (index) without deleting them from your working directory.
- `git reset --hard` resets your working directory and index to the last commit — useful if you want a clean slate.

### ✅ if you want to fix specific files only/If files were added before setting autocrlfto fix that :
- `git rm --cached <filename>` unstages the specific file.
- `git reset HEAD <filename>` resets the file to the last committed state.

Then in both cases:
```bash
git add .
git commit -m "Fix file tracking issue"
git status 
```

---



## 🧪 Nano Editor & File Splitting

Create and edit new file:
```bash
nano Viewer.py
```
Exit Nano: `Ctrl + X`, then `Y`, then `Enter` for  open `'ctr;+s`

To quit Vim:` press Esc`, then type `:wq `and hit` Enter`


Rename file:
```bash
mv GridViewer.py Viewer.py
```

Stage and commit:
```bash
git add Maze.py Viewer.py
git commit -m "Renamed GridViewer module to Viewer"
```

---

## 🛠️ Git Tips & Tools

- 📚 View all Git commands: `git help -a`
- ❓ Help for a command: `git help <command>`
- to see all avialable commnd `git help`
- Use -h for a quick summary:` git config -h`  / `git config --help`
- ✅View all current Git settings: git config --list
- Type the beginning of a command: git config --
- Press Tab → Git shows available options.
- Remove an EMPTY directory  :rmdir <directory_name>
- Remove a directory WITH files): rm -r <dir_name> ⚠ Warning: This permanently deletes files.
- `winpty python Maze.py` to run the file on git bash &` python Maze.py` for VSCODE


---

