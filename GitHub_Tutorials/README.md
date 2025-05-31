# Getting Started with GitHub

This repository contains Python classwork and tutorials for learning and teaching GitHub-based source control.

## Table of Contents

- [Getting Started with GitHub](#getting-started-with-github)
- [Cloning the Repository](#cloning-the-repository)
- [Create a New Folder and Add Files](#create-a-new-folder-and-add-files)
- [Update Existing File](#update-existing-file)
- [Create a Branch](#create-a-branch)
- [Merge a Branch](#merge-a-branch)
- [Switch Between Branches](#switch-between-branches)
- [Cherry Pick Changes](#cherry-pick-changes)
- [Revert Changes](#revert-changes)
- [Markdown Tips](#markdown-tips)
- [Examples](#examples)
- [Brief Project Description](#brief-project-description)

---

## Cloning the Repository

To clone this repository to your local computer, open Command Prompt and run:

```
git clone https://github.com/mkpatel3-github/Python_Classwork
```

---

## Create a New Folder and Add Files

**On Windows Command Prompt:**
- `cd Python_Classwork` — Change directory to your cloned repository.
- `mkdir GitHub_Tutorials` — Create a new folder for tutorials.
- `cd GitHub_Tutorials` — Change to the newly created directory.
- `echo "Getting Started with GitHub" > README.md` — Create a README file with a title.
- `cd ..` — Change back to the previous directory.
- `git add GitHub_Tutorials/README.md` — Stage your new file for commit.
- `git commit -m "Add GitHub_Tutorials/README.md"` — Commit your changes with a message.
- `git push` — Push your changes to GitHub.

---

## Update Existing File

**On Windows Command Prompt:**
- `cd Python_Classwork/GitHub_Tutorials` — Change directory to your cloned repository.
- Make needed changes to `README.md` and save.
- `git status` — See which files have changed before pushing to GitHub.  
  - RED: Changes on your computer, not staged for commit.  
  - GREEN: Changes staged for commit.
- `git add README.md` — Stage your updated file for commit.
- `git commit -m "Update README.md"` — Commit your changes with a message.
- `git push` — Push your changes to GitHub.

---

## Create a Branch

- **Why create a branch?**  
  A branch is your own playground. It lets you try new things, fix mistakes, and get feedback—without risking the main project. When your work is ready, it can be added safely, and the main project is never broken or messy while you’re working.
- **What is the difference between a PR and a branch?**  
  A PR (Pull Request) is a way to review and discuss changes, but the branch is what keeps your work separate and safe until it’s ready. The PR only exists because you made your changes on a branch, not on the main branch itself. This combination—branch for safety, PR for review—is the standard and safest way to work with GitHub.

**On Windows Command Prompt:**
- `git checkout -b new_tutorial_create_a_branch` — Create and switch to a new branch. (No spaces; use - or _ in the name.)
- Make needed changes to files in your branch and save.
- `git add .` — Stage all changes in the current directory and below.
- `git commit -m "Add new Create a Branch Tutorial"` — Commit your changes with a message.
- `git push -u origin new_tutorial_create_a_branch` — Push your local branch to the remote repository.

---

## Merge a Branch

- **When to merge your branch?**  
  You should merge a branch into main when the work on that branch is complete, tested, reviewed, and ready for release.

**On Windows Command Prompt:**
- `git fetch origin` — Fetch the latest changes from the remote repository.
- `git switch main` — Switch to the branch you want to merge into (usually main).
- `git pull origin main` — Pull the latest changes from the remote main branch.
- `git merge --no-ff new_tutorial_create_a_branch` — Merge your branch into main and create a merge commit.
- If there are merge conflicts, resolve them manually, then:
  - `git add <resolved-files>` — Stage resolved files.
  - `git commit -m "Resolve merge conflicts"` — Commit your changes.
- `git push origin main` — Update the remote main branch with your merged changes.
- `git branch -d new_tutorial_create_a_branch` — (Optional) Delete your feature branch locally.
- `git push origin --delete new_tutorial_create_a_branch` — (Optional) Delete your feature branch remotely.

**Summary Table: Command Sequence**

| Step                | Command                          | Purpose                                 |
|---------------------|----------------------------------|-----------------------------------------|
| Update remotes      | `git fetch origin`               | Get latest remote changes               |
| Switch to main      | `git switch main`                | Prepare to merge into main              |
| Update local main   | `git pull origin main`           | Ensure main is up-to-date               |
| Merge feature branch| `git merge feature-branch`       | Combine your changes into main          |
| Resolve conflicts   | Edit files, `git add`, `git commit` | If Git can’t merge automatically    |
| Push main to remote | `git push origin main`           | Share merged changes                    |
| Delete feature branch| `git branch -d feature-branch`  | Clean up local branches                 |

---

## Switch Between Branches

When you need to switch between branches to complete your work, use these commands. Remember to save your work on the current branch.

**On Windows Command Prompt:**
- `git branch` — List all available local branches.
- `git switch main` — Switch to main or your desired branch.
- If you have uncommitted changes that conflict with files on main, Git may prevent you from switching branches. In that case, you should either:
  - Commit your changes,
  - Stash them with `git stash`, or
  - Discard them if you don’t need them.
- `git stash save "meaningful description"` — Save your changes to a stash with a message.
- `git stash list` — Show all your stashes.
- Restore stashed changes:
  - `git stash apply stash@{2}` — Apply stash and keep it.
  - `git stash pop stash@{2}` — Apply stash and remove it.

---

## Cherry Pick Changes

- Use cherry-pick to selectively apply commits from another branch.
- Be careful: by default, cherry-pick merges and commits the changes.

**Typical workflow:**

```
git switch main
git fetch origin
git pull origin main
git log origin/source-branch --oneline
git cherry-pick abc1234
```

- For multiple commits: `git cherry-pick abc1234 def5678`
- For a range: `git cherry-pick abc1234...ghi7890`
- If there are conflicts:

```
git add <resolved-files>
git cherry-pick --continue
```
- To cherry-pick without committing: `git cherry-pick -n abc1234`
- To discard staged changes: `git reset --hard`

**Summary Table**

| Action                                 | Command                        |
|-----------------------------------------|--------------------------------|
| Cherry-pick and commit immediately      | `git cherry-pick abc1234`      |
| Cherry-pick without committing          | `git cherry-pick -n abc1234`   |
| Discard uncommitted cherry-pick changes | `git reset --hard`             |
| Undo a cherry-pick commit               | `git reset --hard HEAD~1`      |
| Abort ongoing cherry-pick (with conflict)| `git cherry-pick --abort`      |

---

## Revert Changes

- To revert changes during cherry-pick or post-merge: `git reset --hard` or `git reset --hard HEAD~1`.
- To restore a file from a specific commit:  
`git restore --source=<commit-id> -- path/to/your/file`
- After restoring, add and commit the file:

```
git add path/to/your/file
git commit -m "Restore file to state from <commit-id>"
```
- To undo all changes made by a specific commit:  
`git revert <commit-id>`

---

## Markdown Tips

- Use `#` for main headings.
- Use `##` for subheadings.
- Separate paragraphs with a blank line.
- Use `-` for bullet points.
- Use `[Link Text](url)` for links.
- Use triple backticks (```

---

## Examples

- [How to Create a Branch](#create-a-branch)
- [How to Merge Branches](#merge-a-branch)
- [How to See Differences](#update-existing-file)

---

## Brief Project Description

This project helps students and teachers learn the basics of GitHub and version control by providing step-by-step examples and exercises.
