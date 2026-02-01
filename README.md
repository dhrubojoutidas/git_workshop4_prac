

---

```markdown
# 🧠 Git Setup Notes — MazeProject

## 🔍 1. Install Git
- Download Git from [git-scm.com](https://git-scm.com)
- Install it on your computer
- Verify installation:
  ```bash

  git --version
  ```

```markdown
# 🔍 2. Configure Git
Set your identity for commits:

```bash

git config --global user.name ""
git config --global user.email ""
```
Verify:
```bash

git config --global --list
```

## 📁 3. Create and Initialize Project Folder
```bash
mkdir MazeProject
cd MazeProject
git init
ls -a  # should show .git folder
```

## 🐍 4. Add Maze.py and Make First Commit
Copy `Maze.py` into this folder, then:
```bash
git status
git add Maze.py
git status
git commit -m "Initial commit."
git status
```

## 💡 What `git add` Does
- Stages your changes (prepares them for commit)
- Does **not** save permanently — that’s what `git commit` does

```

---

Let me know if you want to add more notes about branching, pushing to GitHub, or working with multiple developers — I’ll format those too.


✅  Use git help
	Ø To see all available commands: git help
	Ø To get help for a specific command: git help <commnd>
	Ø   Use -h for a quick summary:git config -h  /git config --help
	Ø  This lists all Git commands :git help -a

✅View all current Git settings: git config --list
	✔ Shows username, email, editor, etc.


✅If You Forget Command Syntax  Use Tab Completion
			§ Type the beginning of a command: git config --
			§ Press Tab → Git shows available options.

✅ Directory Commands (Git Bash / Linux)
.
	 Remove an EMPTY directory  :rmdir <directory_name>
	 Remove a directory WITH files): rm -r <directory_name>
		       ⚠ Warning: This permanently deletes files.



git diff --color --after you finished editing Maze.py and creating GridViewer.py, but before git add, 
git log --branches --graph
git log --oneline --graph --all
git log 
git log  --oneline



# Install Git and verify
git --version

# Configure your identity
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# View current settings
git config -l


Mkdir project
# Go to your project folder  cd   project

# Initialize Git git init

# Add all files :git add .
Git sttaus 

# Commit changes :git commit -m "Initial commit"
Git sttaus 


# Add remote GitHub repo
git remote add origin https://github.com/dhrubojoutidas/git_workshop4_prac.git

# Verify remote
git remote -v

# Rename branch if needed
git branch -M main

# Push to GitHub and set upstream
git push -u origin main



🧭 4. Now modify Maze.py by splitting it into two files


	(1)Using NANO editor   create  new file like
	Write nano GD.py 
	 
	Then  Open nanao editor to edit then close ctrl + s and exit (ctl+x)
	
	To quit Vim: press Esc, then type :wq and hit Enter.
	To quit Nano: press Ctrl + X, then Y, then Enter.
	
	
	(2) ediit maze.py file
	Git status for both file
	git add Maze.py GridViewer.py
	git commit -m "modify Maze.py by splitting it into two separate files."
	Git status
	
	
🧭 Rename GridViewer.py → Viewer.py
		1️⃣ your terminal:mv GridViewer.py Viewer.py
		Or if you want Git to track the rename automatically:git mv GridViewer.py Viewer.py
		
		2️⃣ Update both files
		Open Maze.py and Viewer.py, and change: import GridViewer  to to:import Viewer
		Also change:GridViewer.view(grid) to  to:Viewer.view(grid)
		This makes sure your code still works after the rename.
		
		3️⃣ Stage all changes
		If you used mv, then do this:  git add Viewer.py Maze.py   /git add -A GridViewer.py
		If you used git mv, then just: git add Viewer.py Maze.py Git will automatically detect the rename.
		
		4️⃣ Check status:Run: git status
		You should see something like:
		renamed: GridViewer.py → Viewer.py
modified: Maze.py
		That means Git understands the rename.
		
		5️⃣ Commit the rename: Now commit: git commit -m "Renamed GridViewer module to Viewer."

ISSUE 1:




✅ What Each Setting Does:
	• git config --global core.autocrlf true → Windows-friendly (convert LF to CRLF on checkout).
	•  git config --global core.autocrlf input → Linux/macOS-friendly (keep LF, no conversion on checkout).
	• git config --global core.autocrlf false → No conversion at all (you manage line endings manually).
	

	1. Verify your setting: git config --global core.autocrlf → It should return true.
	will stop that warning because it tells Git to automatically handle line endings for Windows:
		○ When you add files: Git converts CRLF → LF internally.
		○ When you checkout files: Git converts LF → CRLF for Windows
	
	2. Continue your workflow:
		○ Add files: git add Maze.py
		○ Commit: git commit -m "Initial commit"
		○ Push to remote: git push -u origin master

Issue 2:Optional: If you already added files before changing the setting, you might still see the warning for those files. To fix: 
git rm --cached -r .
git reset --hard
Then re-add and commit.

ISSUE 3:The image explains why you might see “Untracked files” like __pycache__ or .pyc files after running Python code. Here’s what it means and what you should do:

✅ What does it mean?
	• When you run Python, it creates:
		○ __pycache__ folder
		○ .pyc files (compiled bytecode)
	• Git sees these as untracked files because they are not part of your repo yet.
	• These files are not needed in Git because they can be regenerated anytime.

✅ Why does Git complain?
	• Git shows them in git status as Untracked files.
	• It’s just a warning, not an error.

✅ How to fix this?

	1. In your project folder, create a file named: .gitignore to tell Git to ignore these files:
	2. Add these lines:
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
	
	3. Stage and commit .gitignore: 
git add .gitignore
git commit -m "Add .gitignore to ignore Python cache files"
	4. winpty python Maze.py to run the file on git bash  or python Maze.py for VSCODE 
Command	What it does	When to use
git push -u origin main	Push + set upstream tracking	First time pushing a branch
git push origin main	Push only	After upstream is already set
		
git branch -M main 		
-m → rename safely -M → rename aggressively (force)

Assuming  Developer 2 is happy to Merge to master and push back to origin :
git checkout master    # swicth to master
git merge change_symbols  # merge another branch 
git push origin master   ✔️ The fix is now merged into master and shared with everyone.





<img width="1548" height="4962" alt="image" src="https://github.com/user-attachments/assets/ce356806-0cd9-4bdc-9850-b96c8cbcfe72" />
