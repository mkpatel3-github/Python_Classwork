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
- `git status` &mdash; See changed file is visible before pushing to github.
- `git add ...` &mdash; Stage your Updated  files for commit. (README.md only specified file)
- `git commit -m "..."` &mdash; Commit your changes with a message.
- `git push` &mdash; Push your changes to GitHub.

---

## Create a Branch

**On Windows Command Prompt**
- `git checkout -b "new_tutorial_create_a_branch"` &mdash; Give Branch Name - No Space, use - or _ in name.
- Make needed changes to files in your branch and save
- `git add .` &mdash; Stage your Updated  files for commit. [git add .]:All changes in current directory and below, [git add -A]:All changes in the entire repository
- `git commit -m "Add new Create a Branch Tutorial"` &mdash; Commit your changes with a message.
- `git push -u origin "new_tutorial_create_a_branch"` &mdash; Push my local branch named new-feature to the remote repository named origin.


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

