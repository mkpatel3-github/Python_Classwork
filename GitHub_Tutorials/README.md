# Getting Started with GitHub
This repository contains Python classwork and tutorials for learning and teaching GitHub-based source control.

## Table of Content
- [Getting Started with GitHub](#getting-started-with-github)
  - [Table of Content](#table-of-content)
  - [Cloning the Repository](#cloning-the-repository)
  - [Create a New Folder and Add Files](#create-a-new-folder-and-add-files)
  - [Update Existing File](#update-existing-file)
  - [Create a Branch](#create-a-branch)
  - [Merge a Branch](#merge-a-branch)
  - [Switch Between Branches](#switch-between-branches)
  - [Cherry Pick Changes](#cherry-pick-changes)
  - [Revert Changes](#revert-changes)
---

## Cloning the Repository

To clone this repository to your local computer, open Command Prompt and run:

git clone https://github.com/mkpatel3-github/Python_Classwork


---

## Create a New Folder and Add Files

**On Windows Command Prompt**
- `cd Python_Classwork` &mdash; Change directory to your cloned repository.
- `mkdir GitHub_Tutorials` &mdash; Create a new folder for tutorials.
- `cd GitHub_Tutorials` &mdash; Change to newly created directory.
- `echo "Getting Started with GitHub" > README.md` &mdash; Create a README file with a title.
- `cd ..` &mdash; Change back to previous directory.
- `git add ...` &mdash; Stage your new file for commit. (GitHub_Tutorials\README.md only specified file)
- `git commit -m "..."` &mdash; Commit your changes with a message.
- `git push` &mdash; Push your changes to GitHub.

---

## Update Existing File

**On Windows Command Prompt**
- `cd Python_Classwork\GitHub_Tutorials` &mdash; Change directory to your cloned repository.
- Make needed changes to README.md and save
- `git status` &mdash; See changed file is visible before pushing to github. RED: Changes on your computer and not saved on PR, GREEN: Changes saved to PR
- `git add ...` &mdash; Stage your Updated  files for commit. (README.md only specified file)
- `git status` &mdash; See changed file is visible before pushing to github. RED: Changes on your computer and not saved on PR, GREEN: Changes saved to PR
- `git commit -m "..."` &mdash; Commit your changes with a message.
- `git push` &mdash; Push your changes to GitHub.

---

## Create a Branch
- Why Create a Branch? A branch is your own playground. It lets you try new things, fix mistakes, and get feedback—without risking the main project. When your work is ready, it can be added safely, and the main project is never broken or messy while you’re working.
- What is the Difference between PR and a Branch? A PR is a way to review and discuss changes, but the branch is what keeps your work separate and safe until it’s ready. The PR only exists because you made your changes on a branch, not on the main branch itself. This combination—branch for safety, PR for review—is the standard and safest way to work with GitHub.

**On Windows Command Prompt**
- `git checkout -b "new_tutorial_create_a_branch"` &mdash; Give Branch Name - No Space, use - or _ in name.
- Make needed changes to files in your branch and save
- `git add .` &mdash; Stage your Updated  files for commit. [git add .]:All changes in current directory and below, [git add -A]:All changes in the entire repository
- `git commit -m "Add new Create a Branch Tutorial"` &mdash; Commit your changes with a message.
- `git push -u origin "new_tutorial_create_a_branch"` &mdash; Push my local branch named new-feature to the remote repository named origin.


---

## Merge a Branch
- When to merge your branch? You should merge a branch into main when the work on that branch is complete, tested, reviewed and ready for release.

**On Windows Command Prompt**
- `git fetch origin` &mdash; Fetch the latest changes from the remote repository to make sure you’re working with the most up-to-date code. This updates your local view of all branches, including main
- `git switch main` &mdash; You need to be on the branch you want to merge into (usually main). Use [git checkout main] for advanced operations, like checking out files or commits, or if you are on an older Git version.
- `git pull origin main` &mdash; Pull the latest changes from the remote main branch to ensure your main is current. This prevents conflicts that may arise from other people’s changes.
- `git merge --no-ff "new_tutorial_create_a_branch"` &mdash; Merge your branch into main and create a merge commit, This command combines the changes from feature-branch into main. If there are no conflicts, Git will create a new merge commit.
- You may run into merge conflict where overlapping changes in same file/line conflict with each other. In such case manually resolve conflict and commit changes.
- `git add <resolved-files>` &mdash; In case of merge conflict: Stage your Updated  files for commit.
- `git commit -m "..."` &mdash; In case of merge conflict: Commit your changes with a message.
- `git push origin main` &mdash; Update the remote main branch with your merged changes, IMPORTANT: This makes your changes visible to everyone.
- `git branch -d feature-branch` &mdash; (Optional) Delete your feature branch locally to reduce number of branch maintainance.
- `git push origin --delete feature-branch` &mdash; (Optional) Delete your feature branch remotely to reduce number of branch maintainance.


**Summary Table : Command Sequence**
|Step | Command | Purpose |
|-----|---------|---------|
|Update remotes | git fetch origin | Get latest remote changes |
|Switch to main | git checkout main | Prepare to merge into main |
|Update local main | git pull origin main | Ensure main is up-to-date |
|Merge feature branch | git merge feature-branch | Combine your changes into main |
|Resolve conflicts | Edit files, git add, git commit | If Git can’t merge automatically |
|Push main to remote | git push origin main | Share merged changes |
|Delete feature branch | git branch -d feature-branch | Clean up local branches |

---

## Switch Between Branches
- When you need to switch between Branches to complete your work, you can do so following these commands. Remember to save your work on current branch.
**On Windows Command Prompt**
- `git branch` &mdash; List all available local branches
- `git switch main` &mdash; switch to main or your desired branch. 
- If you have uncommitted changes that conflict with files on main, Git may prevent you from switching branches. In that case, you should either: Commit your changes, Stash them with [git stash], or Discard them if you don’t need them.
-`git stash save "meaningful description"` &mdash; Always recommended to save stash with meaningful message.
- When you run [git stash save "message"], Git stores your changes in a special local stack and reverts your working directory to the last committed state, making it clean for new tasks.
-`git stash list` &mdash; This shows all your stashes, with the most recent as stash@{0}, the next as stash@{1}, and so on.
- You can later restore your stashed changes with [git stash apply] (which keeps the stash in the stack) or [git stash pop] (which restores and removes the stash from the stack in case only one stash saved).
- By default, [git stash] stashes only tracked files, but you can include untracked/new files with [git stash -u].
-`git stash apply stash@{2}  or  git stash pop stash@{2}` &mdash; Replace 2 with the appropriate stash number.

---

## Cherry Pick Changes
- When you want to selectively pick changes from someone to your branch or your main, you perform this actions. 
- Be careful as default options merges the cherry picked changes and adds them and commits to your existing work.
- First ensure your main is upto date. This will bring your local main branch up to date with the remote main branch, incorporating any new commits or changes that have been made by others.
-```
git switch main  or  git checkout main
git fetch origin
git pull origin main
```
- Identify the commit you want to cherry-pick by viewing the log of the source branch.
-`git log origin/source-branch --oneline` &mdash; Find Commit ID (i.e abc1234) you want to pull.
- Make sure you are on correct branch or main where you want to apply the change.
-`git checkout main`
- NOTE: Below command will merge, add and commit changes.
-`git cherry-pick abc1234` &mdash; Apply abc1234 to main (Relpace abc1234 with correct commit ID).If you want to cherry-pick multiple commits, you can list their hashes: [git cherry-pick abc1234 def5678] Or cherry-pick a range: [git cherry-pick abc1234...ghi7890]
- If there are conflicts, Git will pause and ask you to resolve them. After resolving conflict manually, continue: 
```
git add <resolved-files>
git cherry-pick --continue
```
- After cherry-picking, push your updated changes to remote.
-`git push origin main` &mdash; Pushes your changes to Remote.
If you want to apply the changes for experimentation but not commit right away, use the --no-commit (or -n) option. 
-`git cherry-pick -n abc1234`
- Later you may [git add .,git commit -m "..."] to commit merged changes. Or discard the staged and working directory changes [git reset --hard].

**Summary Table**
| Action | Command |
|--------|---------|
|Cherry-pick and commit immediately	| git cherry-pick abc1234 |
|Cherry-pick without committing	| git cherry-pick -n abc1234 |
|Discard uncommitted cherry-pick changes (-n option only) | git reset --hard |
|Undo a cherry-pick commit | git reset --hard HEAD~1 |
|Abort ongoing cherry-pick (with conflict) | git cherry-pick --abort |

---

## Revert Changes
- As you saw in previous section, if you want to revert changes during cherry-pick or post merge, use [git reset --hard  or gitreset --hard Head~1] options. This will reset full branch.
- You can use [git restore] to bring back the file from a specific commit, without affecting the rest of your branch.
-`git restore --source=<commit-id> -- path/to/your/file` &mdash; pick commit-id you want file to be restored. Give relative path if working from home directory, or file name if working from current directory.
- Don't forget to add file [git add path/to/your/file] and commit file [git commit -m "Restore file to state from <commit-id>"]
- If you want to undo all changes made by a specific commit (not just one file), use git revert.
-`git revert <commit-id>` &mdash; This creates a new commit that undoes the changes from the specified commit, keeping your history safe.

---
## Markdown Tips

- Use `#` for main headings.
- Use `##` for subheadings.
- Separate paragraphs with a blank line.
- Use `-` for bullet points.
- Use `[Link Text](url)` for links.
- Use triple backticks (\`\`\`) for code blocks, specifying the language for syntax highlighting.

---

## [Examples](#examples)

- [How to Create a Branch](#how-to-create-a-branch)
- [How to Merge Branches](#how-to-merge-branches)
- [How to See Differences](#how-to-see-differences)

---

## Brief Project Description

This project helps students and teachers learn the basics of GitHub and version control by providing step-by-step examples and exercises.

