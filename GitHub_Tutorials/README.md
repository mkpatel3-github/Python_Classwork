# Getting Started with GitHub

This repository contains Python classwork and tutorials for learning and teaching GitHub-based source control.

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
- `git branch` &mdash; To find out local branches
- `git branch -r` &mdash; To find out remote branches
- Make needed changes to files in your branch and save
- `git add .` &mdash; Stage your Updated  files for commit. [git add .]:All changes in current directory and below, [git add -A]:All changes in the entire repository
- `git commit -m "Add new Create a Branch Tutorial"` &mdash; Commit your changes with a message.
- `git push -u origin "new_tutorial_create_a_branch"` &mdash; Push my local branch named new-feature to the remote repository named origin.
- `git branch` &mdash; To find out local branches
- `git branch -r` &mdash; To find out remote branches
- `git branch` &mdash; To find out local branches
- `git branch -r` &mdash; To find out remote branches
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

