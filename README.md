
# 🌱 Git Tutorials – Step-by-Step Guide

## 1. 📁 Create a Project Folder and Add `README.md`
- Go to your Desktop and create a folder (e.g., `GitTutorials`).
- Open **VS Code**, then use `File → Open Folder` to open this folder.
- Inside VS Code, create a file named `README.md`.

---

## 2. 📂 Navigate to Folder in CMD
- Copy the folder path from the address bar.
- In CMD, type:
  ```bash
  cd path_to_your_folder
  ```
- Example:
  ```bash
  cd Desktop\GitTutorials
  ```

---

## 3. 🔧 Initialize Git and Configure Identity
```bash
git init
git config --global user.name "Rudra Chouhan"
git config --global user.email "rudrachouhan0305@gmail.com"
```
> These settings tell Git who you are and help authenticate with GitHub.

---

## 4. 🔍 Check Status and Add File
```bash
git status
```
> You'll see `README.md` listed as an **untracked file**.

Add it to the staging area:
```bash
git add README.md
```
Check status again:
```bash
git status
```
> Now it will show `Changes to be committed`.

---

## 5. ✅ Commit the File
```bash
git commit -m "first commit"
git status
```
> Now Git says: *“nothing to commit, working tree clean”*.

---

## 6. 🌳 Rename Branch from Master to Main
```bash
git branch
# Shows 'master'

git branch -M main
git branch
# Now it shows 'main'
```

---

## 7. 🌐 Connect to GitHub Repository
```bash
git remote add origin https://github.com/RudraChouhan03/gittutorials.git
git remote -v
```
> This connects your local repo to the GitHub repo.

---

## 8. ⬆️ Push to GitHub
```bash
git push origin main
```
> All committed files will be pushed to the remote repository.

---

# Resolving Git Push Rejection Due to Remote Changes

When you try to push and see this error:

```bash
git push origin main
```
To https://github.com/YourUsername/your-repo.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/YourUsername/your-repo.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.

- It occurs because someone has made the changes in the file and we are trying to overwrite his changes by pushing. So to resolve this 

> 1. Pull Remote Changes with Rebase
```bash
git pull origin main --rebase
```

If there is a conflict (e.g., in README.md), Git will show:
```
bash
CONFLICT (content): Merge conflict in README.md
```
> 2. Open and Fix the Conflicted File (it will open in vs)
Use any editor to open the file:

```
bash
code README.md
```

> We'll see something like this:

```
txt		
<<<<<<< HEAD
Content from the remote branch
=======
Content from your local commit
>>>>>>> a17cd37... this is my second commit
```

> 📝 Manually edit the content:

- Keep what you want (either one side or both).

- Remove the markers <<<<<<<, =======, and >>>>>>>.

> 3. Mark Conflict as Resolved

```
bash
git add README.md
```

> 4. Continue the Rebase

```
bash
git rebase --continue
```

> 5. Push Your Changes

- After the rebase finishes successfully:
```
bash
git push origin main 
```

---

## 9. 📝 Make Changes to README.md
- Open `README.md` using **Notepad** by dragging the file into it.
                            or
- Open `README.md` from **Notepad** by open with **Notepad**
- Edit the file, save, and close Notepad.
- Check Git status:
  ```bash
  git status
  ```
> Shows "modified: README.md".

### 🗑️ Discard Changes
To undo the changes in the file before committing:
```bash
git restore README.md
```
> The file returns to its last committed state.

### 🧺 Stage and Commit the Change if want to add the changes
```bash
git add README.md
git commit -m "Updated README"
git push origin main
``` 

---

## 11. 📂 Add and Commit Multiple Files
If there are many new/modified files:
```bash
git add .
git commit -m "this is my second commit"
git push origin main
```

---

## 12. 📥 Clone a Repository
1. Create a new folder anywhere.
2. In CMD:
   ```bash
   cd folder_path
   ```
3. Clone the repo:
   ```bash
   git clone https://github.com/RudraChouhan03/gittutorials.git
   ```
> This creates a copy of the repository with all files inside.

---

## 13. ➕ Add New File in Cloned Folder and Push
Inside the repository:
```bash
git add .
git commit -m "this is my third commit"
git push origin main
```
> New file gets added to GitHub repository.

---

## 14. 🔢 Check Commit Count
On the GitHub repository page:
- Below the green `Code` button, you can see **number of commits**.
- Click on it to view the commit history.

---

## 15. 🔍 View Differences Between File Versions

### `git diff`

```bash
git diff
```

> Shows the **difference between the working directory and the staging area**.  
> (i.e., what has changed but is **not yet staged** using `git add`)

---

### `git diff --staged`

```bash
git diff --staged
```

> Shows the **difference between the staging area and the last commit**.  
> (i.e., what is **staged** and ready to be committed but **not yet committed**)

---

## 16. 💾 Commit Staged Changes

### `git commit -m "[descriptive message]"`

```bash
git commit -m "your commit message"
```

> Creates a **commit snapshot** of the current staging area with a message describing the changes.

---

## 17. 🌿 Branch Management

### `git branch`

```bash
git branch
```

> Lists all local branches.  
> A `*` symbol marks the **currently active branch**.

---

### `git branch [branch-name]`

```bash
git branch feature-x
```

> Creates a **new branch** named `feature-x` at the current commit.  
> (You’ll still be on the current branch until you switch.)

---

## 18. 🔀 Switching Between Branches

### `git checkout [branch-name]`

```bash
git checkout feature-x
```

> Switches to the specified branch and updates your working directory.

---

## 19. 🔗 Merging Branches

### `git merge [branch-name]`

```bash
git merge feature-x
```

> Merges the changes from `feature-x` into your **current branch**.

---

## 20. 📜 View Commit History

### `git log`

```bash
git log
```

> Shows a list of all commits in the current branch, including:

* Commit hash
* Author
* Date
* Commit message

> If we want to see last three commits then 

```bash
git log -p -3
```

> To come out if no sign of entering anything press Q

---




