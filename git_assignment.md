1. Staging all changes and committing with a meaningful message
git add .                          # Stages all changes (new, modified, deleted files)
git commit -m "Your meaningful commit message here"

2. Committed to the wrong branch: move commits to the correct branch
# Step 1: Checkout the correct branch (create if not exists)
git checkout main

# Step 2: Cherry-pick commits from the wrong branch
# Find the commit hashes using `git log` on the wrong branch
git cherry-pick <commit_hash>

# Step 3: Remove commits from the wrong branch
git checkout wrong-branch
git reset --hard HEAD~n  # n = number of commits to remove

3. Create a new branch, make changes, and push to GitHub
# Step 1: Create and switch to the new branch
git checkout -b feature-branch

# Step 2: Stage and commit changes
git add .
git commit -m "Add feature implementation"

# Step 3: Push to GitHub
git push origin feature-branch

4. Contribute to an open-source project (fork → pull request)
Fork the repository from GitHub.

Clone the forked repo to your machine:
git clone https://github.com/your-username/project.git
cd project

Create a new branch for your changes:
git checkout -b fix-issue-123

Make changes and commit:
git add .
git commit -m "Fix bug in XYZ functionality"

Push the branch:
git push origin fix-issue-123

Create a pull request from your forked repo to the original repo on GitHub.

Collaborate via GitHub PR reviews.

5. Resolve merge conflicts between your branch and main
# Step 1: Switch to your feature branch
git checkout feature-branch

# Step 2: Merge main into your branch
git pull origin main

# If conflicts occur:
# Git will show files with conflicts. Open them and resolve manually.

# Step 3: After resolving, add the resolved files
git add .

# Step 4: Commit the merge
git commit -m "Resolved merge conflicts with main"

# Step 5: Push changes
git push origin feature-branch


6. Create a feature branch based on the latest main
git checkout main
git pull origin main                # Get the latest main changes
git checkout -b new-feature-branch # Create and switch to the new branch

7. Revert to a specific commit (discard everything after it)
# Option 1: Hard reset (permanent loss of newer commits)
git reset --hard <commit_hash>

# Option 2: Soft reset (keep changes staged)
git reset --soft <commit_hash>

# Option 3: Checkout a specific commit (to inspect)
git checkout <commit_hash>

8. Restore a deleted file from the previous commit
# Step 1: Find the file path and commit hash if needed
# Step 2: Restore the file from the previous commit
git checkout HEAD^ -- path/to/deleted-file

# Step 3: Add and commit the restored file
git add path/to/deleted-file
git commit -m "Restore accidentally deleted file"


