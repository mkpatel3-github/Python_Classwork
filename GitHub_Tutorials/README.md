# Getting Started with GitHub

This repository contains Python classwork and tutorials for learning and teaching GitHub-based source control.

---

## Cloning the Repository

To clone this repository to your local computer, open Command Prompt and run:

git clone https://github.com/mkpatel3-github/Python_Classwork


---

## Create a New Folder and Add Files

### On Windows Command Prompt

cd Python_Classwork
mkdir GitHub_Tutorials
cd GitHub_Tutorials
echo "Getting Started with GitHub" > README.md
cd ..
git add GitHub_Tutorials\README.md
git commit -m "Getting Started with GitHub"
git push

---

## Update Existing File

### On Windows Command Prompt

cd Python_Classwork\GitHub_Tutorials
make needed changes to README.md
git status
git add README.md
git commit -m "Updating README.md with new example"
git push

---

**Explanation:**
- `cd Python_Classwork` &mdash; Change directory to your cloned repository.
- `mkdir GitHub_Tutorials` &mdash; Create a new folder for tutorials.
- `echo Getting Started with GitHub > README.md` &mdash; Create a README file with a title.
- `git add ...` &mdash; Stage your new file for commit.
- `git commit -m "..."` &mdash; Commit your changes with a message.
- `git push` &mdash; Push your changes to GitHub.

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

