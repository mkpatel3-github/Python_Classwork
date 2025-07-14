# 🎯 Git Command Cheat Sheet for Young Developers

## 🚀 Getting Started
git clone [url] # Copy repository to your computer
git status # Check what's changed
git log --oneline # See commit history (short)
git log --graph # See commit history (visual)

text

## 💾 Saving Your Work
git add [filename] # Stage specific file
git add . # Stage all changes
git commit -m "message" # Save changes with message
git push # Upload to GitHub
git push origin [branch-name] # Upload specific branch

text

## 🌳 Working with Branches
git branch # List all branches
git branch [branch-name] # Create new branch
git checkout [branch-name] # Switch to branch
git checkout -b [branch-name] # Create and switch to new branch
git switch [branch-name] # Switch to branch (newer command)
git merge [branch-name] # Combine branches
git branch -d [branch-name] # Delete branch



## 🤝 Collaboration Commands
git fetch # Download updates from GitHub
git pull # Download and merge updates
git pull origin main # Get latest main branch
git push origin [branch-name] # Share your branch



## 🔄 Undoing Changes
git checkout -- [filename] # Restore file from last commit
git reset --hard HEAD # Restore everything to last commit
git reset --soft HEAD~1 # Undo last commit (keep changes)
git reset --hard HEAD~1 # Undo last commit (lose changes)



## 🏷️ Special Operations
git stash # Temporarily save changes
git stash pop # Restore temporarily saved changes
git cherry-pick [commit-id] # Copy specific commit
git rebase main # Move your branch to latest main



## 🆘 Emergency Commands
git reflog # See all recent actions
git checkout [commit-id] # Go back to specific commit
git reset --hard origin/main # Reset to match GitHub main



---
*Keep this handy during your Git journey! 📖*