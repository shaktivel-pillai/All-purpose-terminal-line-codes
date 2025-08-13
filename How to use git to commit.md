######  {Git Cheat Sheet: Commit & Push to GitHub via Terminal}

## Initial Setup (Run Once Per Repository)
1. **Open your terminal**
2. **Navigate to your project folder:**
```
cd /path/to/your/project
```
3. **Initialize Git**:
```
git init
```
 4. **Initialize a new Git repository in your current folder.**
 ```
 git remote add origin https://github.com/your-username/your-repo-name.git
```

##  Daily Workflow: Commit & Push Changes

##### 1. Check the status of your files
```
git status
```
- Shows which files have been modified, added, or deleted.
##### 2. Add files to staging
```
git add .
```
- the `.` is important and it stages all changed files for commit. You can also use `git add filename` to stage specific files.
##### 3. Commit your changes
```
git commit -m "Your descriptive commit message"
```
- Saves a snapshot of your staged changes with a message explaining what you did.
##### 4. Pull remote changes before pushing
```
git pull origin master --rebase
```
- Fetches and integrates changes from the remote `master` branch. `--rebase` keeps your history clean by applying your changes on top of the latest remote commits.
##### 5. Push your changes to GitHub
```
git push origin master
```

## Optional: First-time push with upstream tracking
```
git push -u origin master
```
- Sets the default remote and branch so future pushes can be done with just `git push`.
## Other Useful Commands

##### View commit history
```
git log --oneline
```
- Shows a compact list of past commits.

##### See differences before committing
```
git diff
```
- Displays changes between your working directory and the last commit.

##### Undo last commit (without losing changes)
```
git reset --soft HEAD~1
```
- Moves the last commit back to staging so you can edit or recommit.