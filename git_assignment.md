# Git Assignment

---

## 1. Staging all changes and committing with a meaningful message

```bash
# 1. Staging all changes and committing with a meaningful message
git add .                      # Stages all changes (new, modified, deleted)
git commit -m "Your meaningful commit message here"
```

---

## 2. Committed to the wrong branch: move commits to the correct branch

```bash
# 2. Committed to the wrong branch: move commits to the correct branch

# Step 1: Checkout the correct branch (create if it doesn’t exist)
git checkout main

# Step 2: Cherry-pick commits from the wrong branch
git log                         # Get the commit hash
git cherry-pick <commit_hash>  # Apply each commit to the correct branch

# Step 3: Remove the commits from the wrong branch
git checkout wrong-branch
git reset --hard HEAD~n        # n = number of commits to remove
```

---

## 3. Create a new branch, make changes, and push to GitHub

```bash
# 3. Create a new branch, make changes, and push to GitHub
git checkout -b feature-branch             # Create and switch to new branch
git add .                                  # Stage changes
git commit -m "Add feature implementation" # Commit
git push origin feature-branch             # Push to GitHub
```

---

## 4. Contribute to an open-source project (Fork → Pull Request)

```bash
# 4. Contribute to an open-source project (fork → pull request)

# Fork the repository on GitHub, then:

# Step 1: Clone your forked repo
git clone https://github.com/your-username/project.git
cd project

# Step 2: Create a new branch
git checkout -b fix-issue-123

# Step 3: Make changes, commit and push
git add .
git commit -m "Fix bug in XYZ functionality"
git push origin fix-issue-123

# Step 4: Go to GitHub and create a pull request from your fork
```

---

## 5. Resolve merge conflicts between your branch and main

```bash
# 5. Resolve merge conflicts between your branch and main

# Step 1: Switch to your feature branch
git checkout feature-branch

# Step 2: Merge latest main into your branch
git pull origin main

# If conflicts occur:
# Git will mark conflicting files — open and resolve them manually

# Step 3: After resolving, add and commit
git add .
git commit -m "Resolved merge conflicts with main"
git push origin feature-branch
```

---

## 6. Create a feature branch based on the latest main

```bash
# 6. Create a feature branch based on the latest main
git checkout main
git pull origin main                   # Update local main
git checkout -b new-feature-branch     # Create and switch to new branch
```

---

## 7. Revert to a specific commit (discard all changes after)

```bash
# 7. Revert to a specific commit (discard all changes after)

# Option 1: Hard reset (permanently remove newer commits)
git reset --hard <commit_hash>

# Option 2: Soft reset (keep changes staged)
git reset --soft <commit_hash>

# Option 3: Checkout a specific commit (detached state)
git checkout <commit_hash>
```

---

## 8. Restore a deleted file from the previous commit

```bash
# 8. Restore a deleted file from the previous commit

# Step 1: Restore the file
git checkout HEAD^ -- path/to/deleted-file

# Step 2: Add and commit the restored file
git add path/to/deleted-file
git commit -m "Restore accidentally deleted file"
```

---

