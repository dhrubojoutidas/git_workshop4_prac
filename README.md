## 🔧 1. Install Git
- 📥 Download Git from [git-scm.com](https://git-scm.com)
- 💻 Install &  Verify installation: git --version
- sudo apt-get install git
---

## 🧑‍💻 2. Configure Git Identity
Set your name and email (used for commits):
```bash
-  git config --global user.name "dhrubojoitidas"
- `git config --global user.email "dhrubotroyee20@gmail.com"`
- `git config --global color.ui auto ` : Enable some colorization of Git output.
```
---

## 📁 3. Create Project Folder & Initialize Git
```bash
`mkdir MazeProject`
`cd MazeProject`
`git init`
` ls -a ` # should show: .  ..  .git
git status
`git add Viewer.py Maze.py` / `git add -A GridViewer.py`
git status
git commit -m "Initial commit."
git status
```

---

## 🔀 5. Rename Branch & Push to GitHub
```bash

- git branch -M main means `-m → rename safely` & `-M → rename aggressively (force)
-  `Create a New Branch  `: git branch updating_amze 
-  Switch to New Branch : ` git checkout branch2 `
- ` git branch [-a]  `
-  Create and Switch in One Step: ` git checkout [-b][branch_name] `
- Merge Branch into Main  : `git merge  mynewbranch `
- Shows all commits in the current branch’s history: `git log`
-  List All Branches `git branch`
-  Display Current Branch Name : `git status `
-  Rename a Branch :  `git branch -m mynewbranch featurexyz  (Renames mynewbranch to featurexyz.) `
-  Create a Branch from a Specific Commit:`git branch mynewbranch ff823e `
-  Del  from GITHUB REPO /remote: `git push origin --delete (branch name) `
-  Delete Branches : ` git branch -d mynewbranch.` You can delete branches, usually after merging use -D instead of -d forces deletin<



```

-  Merge to master and push back to origin :
```bash
- git checkout master    # swicth to master
- git merge change_symbols  # merge another branch
- git push -u origin main  | Push + set upstream tracking |First time pushing a branch
- git push  origin main| Push only |After upstream is already set ✔️ now merged into master &shared with everyone.
- git merge
``` 
---

##  6 🔀 Important Concept: Fetch vs Merge 

-What git fetch does
  - Downloads updates from the remote
  - Does not modify your current branch
  - What git merge does:Integrates changes into your current branch
  - git pull= fetch + merge

---

## 7 👥  Connect to GitHub Remote Repo
```bash
- create a git repo like git_workshop_prac4
- after creating repo copy REPO  URL :https://github.com/dhrubojoutidas/pro1.git
- go to  local folder : cd project
- git init
- gtu add .
- git commit -m "     "
- to connect with github :git remote add origin https://github.com/dhrubojoutidas/git_workshop4_prac.git
- git remote -v
- you should see somting [----- fetch] [push ]
- rename branch : git brach -M main/master
- push to github : git push -u origin main/master
```
--- 

##  👥 Two-Developer Simulation

---
### 🧑‍💻 Developer 1: Clone remote repo, cretae B , commit and push

```bash
- cd 
- git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git myproject2
- Cd myproject2
- Create and switch to a new branch: `git checkout -b change_symbols`
- #Edit Maze.py
-git add .
-git commit -m "Change symbols in text"
- push the new B to the remote : git push -u origin change_symbols

What this does
			i. Creates a new directory called myproject2
			ii. Copies the full repository history
			iii. Automatically sets:origin → remote repository
📌 Note: A bare repository cannot be worked on directly — cloning creates a working copy.
✔️ The remote repository now has a new branch created by Developer 1.

```
---

### 🧑‍💻 Developer 2: Clone, Fetch & Switch
---

```bash
Clone the GitHub repo into a new folder.This will simulate Developer 2 getting the latest code:
- cd 
-git clone https://github.com/dhrubojoutidas/git_workshop4_prac.git dev_2_project_folder
- cd dev_2_project_folder
- Fetch updates from GitHub3 remote :`git fetch origin
- git checkout change_symbols
- git  log --oneline  ✅ Now Developer 2 sees the changes made by Developer 1.
```
---

##  10🧹 Ignore Python Cache Files 

---
in your project folder Create  NANO EDITOR `.gitignore`  to tell Git to ignore these files::
```
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
git add .gitignore  |  git  & git commit -m "Added .gitignore to ignore Python cache files" |
```

---


Create and edit new file: `Nano Viewer.py` 
`Exit Nano: `Ctrl + X`, then `Y`, then `Enter` for  open ` ctr;+s` 
To quit Vim:` press Esc`, then type `:wq `and hit` Enter`


## 11 ⚙️ Line Ending Settings (Windows vs Linux)
---
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/e097fecb-dcc2-40df-af66-32dd19f12628" />


- ` git config --global core.autocrlf true ` # Windows-friendly (convert LF to CRLF on checkout)
- `git config --global core.autocrlf input ` #✅ Linux/macOS-friendly (keep LF, no conversion on checkout).
- ` git config --global core.autocrlf false ` # ✅ No conversion at all (you manage line endings manually)
- Continue your workflow: ` Add files: git add Maze.py &  Commit: git commit -m "Initial commit" `
```bash

```
 ### 🔧To stop that warning because it tells Git to automatically handle line endings for Windows:
-  When you add files: Git converts CRLF → LF internally.
-  When you checkout files: Git converts LF → CRLF for Windows

---

## 12 🛠️ Git Tips & Tools

---
- 📚 View all Git commands: `git help -a`
- ❓ Help for a command: `git help <command>`
- to see all avialable commnd `git help`
- Use -h for a quick summary:` git config -h`  / `git config --help`
- ✅View all current Git settings: `git config --list`
- Type the beginning of a command:` git config --`
- Press Tab → Git shows available options.


---
Rename file:
- `mv GridViewer.py Viewer.py`  in terminal
- `git mv GridViewer.py Viewer.py ` if you want Git to track the rename automatically
- ` git add Maze.py Viewer.py & git commit -m "Renamed GridViewer module to Viewer" `

```
  
- Remove an EMPTY directory  :`rmdir <directory_name>`
- Remove a directory WITH files):`rm -r <dir_name> `⚠ Warning: This permanently deletes files.
- `git rm [file]`   #  delete the file from project and stage the removal for commit
-  `winpty python Maze.py` to run on git bash &` python Maze.py` for VSCODE
- `git rebase [branch]  `  apply any commits of current branch ahead of specified one
- `git revert [commit sha]` Create a new commit, reverting changes from specified commit. 

---

### ✅ Use this if you want to fix **all previously added files**:

- `git rm --cached -r .` removes all files from the staging area (index) without deleting them from your working directory.
- `git reset --hard` resets your working directory and index to the last commit — useful if you want a clean slate.

### ✅ if you want to fix specific files only/If files were added before setting autocrlfto fix that :
- `git rm --cached <filename>` # Unstage all files without deleting them
- `git reset HEAD <filename>` resets the file to the last committed state.
- `git reset [file] `:unstage a file while retaining the changes in working directorY
- then git add, commit and status
``` 
---

## 13 verifications 
```bash
 - after you finished editing Maze.py and creating GridViewer.py, but before git add,` git diff --color `
 - ` git log --oneline --graph --decorate`
 - `git log --branches --graph`
 - `git log --oneline --graph --all`
 - `git log  --oneline`
 - `git log ` #  show the commit history for the currently active branch
 - ` git reflog ` List operations (e.g. checkouts or commits) made on local repository
 - `git log --stat -M ` #  show all commit logs with indication of any paths that moved
 - `git log branchB..branchA  `   show the commits on branchA that are not on branchB
 -` git log --follow [file] `   show the commits that changed file, even across renames
 - `git diff branchB..branchA `    show the diff of what is in branchA that is not in branchB
 - `git show [SHA] `    show any object in Git in human-readable format
 - `git log [-n count]` List commit history of current branch. -n count limits list to last n commits.
 - `git log --oneline --graph --decorate` An overview with reference labels and history graph. One commit per line.
 - `git log ref..` List commits  present on  current branch & not merged into ref. A ref can be a branch name or a tag 
 - `git reflog `List operations (e.g. checkouts or commits) made on local repository
 - ` git stash `  Put current changes in your working directory into stash for later use.
 -  `git stash list `   list stack-order of stashed file changes
 - ` git stash pop `  Apply stored stash content into working directory, and clear stash.
 -  `git stash drop `    discard the changes from top of stash stack
 - git stash apply (useful to know) # Apply the latest stash but keep it in the stash list.
		
```

---

## 14 TAG 
	🧠 Why this matters
		○ Tags preserve the history of your work
		○ Deleting unused branches keeps your project clean 
		This is good Git hygiene — especially for team projects
	1️⃣ This creates a permanent label so you can refer back to the work later.	These tags are just names — archive/ is a naming convention to show they’re archived.
- 

06 Tagging known commits
```bash 
 - git tag   List all tags.
 - git tag [name] [commit sha]   #Create a tag reference named name for current commit. Add commit sha to tag a specific commit instead of current one.
- git tag -a [name] [commit sha]   #Create a tag object named name for current commit.
- git tag -d [name]   #Remove a tag from local repository.
 -git push [--tags] [remote]   Push local changes to the remote. Use --tags to push tags.
- git tag:  List all tags. #	archive/updating_maze #archive/updating_messages
- `git diff` :diff of what is changed but not staged
-  `git diff --staged` :diff of what is staged but not yet committed




```


	
	





