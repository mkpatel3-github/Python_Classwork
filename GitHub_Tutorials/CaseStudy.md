# Working as a Team with Branches

Here’s a clear explanation of when to use branches in team projects, and a step-by-step guide for common collaboration workflows.

Branches are for teams where all members have write access to the same repository. Each feature or bugfix gets its own branch, which is later merged back to `main`. This is ideal for small, trusted teams and private projects.

---

# Table of Contents

- [Working as a Team with Branches](#working-as-a-team-with-branches)
  - [Team Project: Create a PR from Your Branch](#team-project-create-a-pr-from-your-branch)
  - [Common Scenario: Verify a Team Member’s PR](#common-scenario-verify-a-team-members-pr)
  - [Common Scenario: Combine a Friend's PR with Your Feature Branch](#common-scenario-combine-a-friends-pr-with-your-feature-branch)
  - [Summary Table](#summary-table)
- [How to Update a Pull Request (PR) After Receiving Feedback](#how-to-update-a-pull-request-pr-after-receiving-feedback)
  - [Step-by-Step: Update Your PR After Feedback](#step-by-step-update-your-pr-after-feedback)
    - [1. Ensure You’re on the Correct Branch](#1-ensure-youre-on-the-correct-branch)
    - [2. Pull Latest Changes (Optional but Recommended)](#2-pull-latest-changes-optional-but-recommended)
    - [3. Make the Required Changes](#3-make-the-required-changes)
    - [4. Stage and Commit Your Changes](#4-stage-and-commit-your-changes)
    - [5. Push Your Changes to the Same Branch](#5-push-your-changes-to-the-same-branch)
    - [6. Your PR is Automatically Updated](#6-your-pr-is-automatically-updated)
  - [Summary Table](#summary-table-1)
  - [Extra Tips](#extra-tips)

---

## Team Project: Create a PR from Your Branch

**Small Teams (All Have Write Access) – Branch-Based Workflow**

1. **Clone the main repository:**
    ```
    git clone https://github.com/your-org/project.git
    cd project
    ```

2. **Create a new branch for your feature or fix:**
    ```
    git checkout -b feature/my-feature
    ```

3. **Or, list all branches and switch to one of them, then rebase with the latest code for that feature branch:**
    ```
    git branch -a
    git switch feature/new-feature   # or: git checkout feature/new-feature
    git pull origin feature/new-feature
    ```

4. **Work on your changes and commit them:**
    ```
    git add .
    git commit -m "Describe your change"
    ```

5. **Push your branch to the shared repository:**
    ```
    git push origin feature/my-feature
    ```

6. **Open a Pull Request (PR) from your branch to `main`:**
    - Go to the GitHub webpage, select your branch, and create a PR.
    - After review, the PR is merged into `main` by a team member.

**Summary:**  
Each team member creates branches in the same repo. Merges happen via PRs to `main`.

**What Gets Merged?**  
Team members merge their feature branches into `main` (or a development branch) via PRs.

---

## Common Scenario: Verify a Team Member’s PR

**Fetch and check out a team member’s Pull Request (PR)**
- `git fetch origin pull/123/head:pr-123`: Downloads the changes from PR #123 on the remote (`origin`) and creates a new local branch called `pr-123` with those changes. It does not affect your current branch.
- `git checkout pr-123`: Switches your working directory to the new local branch `pr-123`, so you can review, test, or work with the PR code.

**When Should You Use This?**
- When you want to review, test, or build upon a team member’s PR before it’s merged.
- When you want to see the PR’s code in your local environment, possibly to help resolve conflicts or test integration with your own feature branch.

---

## Common Scenario: Combine a Friend's PR with Your Feature Branch

1. **Make sure both branches are up to date, and check out your feature branch:**
    ```
    git fetch origin
    git checkout feature/my-feature
    ```

2. **Merge the PR branch into your branch:**
    ```
    git merge pr-123
    ```
    Now your branch contains both your changes and the PR’s changes. Resolve any conflicts if prompted.

---

## Summary Table

| Action                                  | Command                                               |
|------------------------------------------|-------------------------------------------------------|
| Fetch PR #123 as a local branch          | `git fetch origin pull/123/head:pr-123`               |
| Switch to the PR branch                  | `git checkout pr-123`                                 |
| Merge PR branch into your feature branch | `git checkout feature/my-feature`<br>`git merge pr-123` |

---

**Always create a new branch (do not work directly on `main`) for each feature or fix, and merge changes to `main` via PRs.**

---

# How to Update a Pull Request (PR) After Receiving Feedback

When you receive feedback on your Pull Request (PR), you should update your PR by making changes on the **same branch** you used to create the PR. Follow these steps:

---

## Step-by-Step: Update Your PR After Feedback

### 1. Ensure You’re on the Correct Branch

Switch to the branch you used for the PR (if you’re not already on it):

```
git checkout your-feature-branch
```


---

### 2. Pull Latest Changes (Optional but Recommended)

Get the latest changes from the remote branch, especially if others may have made changes:

```
git pull origin your-feature-branch
```

If you need to update your branch with changes from `main` (to resolve conflicts or stay up to date):

```
git fetch origin
git rebase origin/main

or, if you prefer merge:
git merge origin/main
```

(Resolve any conflicts if prompted, then continue.)

---

### 3. Make the Required Changes

Edit your files as needed to address the reviewer’s comments.

---

### 4. Stage and Commit Your Changes

Add and commit your changes with a descriptive message:

```
git add .
git commit -m "Address PR feedback: [describe what you changed]"
```


---

### 5. Push Your Changes to the Same Branch

Push your updates to the remote branch (the same branch as your PR):

```
git push origin your-feature-branch
```

---

### 6. Your PR is Automatically Updated

GitHub automatically updates your open PR with any new commits you push to the branch.  
You do **not** need to create a new PR—just push to the same branch, and the PR will refresh with your latest changes.

---

## Summary Table

| Step                        | Command/Action                                    |
|-----------------------------|---------------------------------------------------|
| Switch to your branch       | `git checkout your-feature-branch`                |
| Pull latest changes         | `git pull origin your-feature-branch`             |
| (Optional) Rebase with main | `git fetch origin`<br>`git rebase origin/main`    |
| Edit files                  | Make code changes in your editor                  |
| Add changes                 | `git add .`                                       |
| Commit changes              | `git commit -m "Address PR feedback"`             |
| Push to remote              | `git push origin your-feature-branch`             |
| Refresh PR                  | **No action needed—GitHub updates it automatically** |

---

## Extra Tips

- If your branch is out of sync with `main`, you may see an “Update branch” button on GitHub. You can use that, or rebase/merge locally and push.
- If you want to combine all feedback into a single commit (for a cleaner history), you can use `git commit --amend` or interactive rebase, but for most cases, just pushing new commits is fine.

---

**In summary:**  
Make your changes locally on the same branch, commit, and push. Your PR will automatically update and show your new changes to reviewers. No need to create a new PR.

