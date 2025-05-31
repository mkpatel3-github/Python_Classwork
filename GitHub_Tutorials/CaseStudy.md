# Working as a Team with Branches

Here’s a clear explanation of when to use branches in team projects, and a step-by-step guide for common collaboration workflows.

Branches are for teams where all members have write access to the same repository. Each feature or bugfix gets its own branch, which is later merged back to `main`. This is ideal for small, trusted teams and private projects.

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
