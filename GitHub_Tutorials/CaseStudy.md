# Working as a Team with Branches
Here’s a clear explanation of when to use branches in team projects, and a step-by-step guide for common collaboration workflows:

- Branches are for teams where all members have write access to the same repository. Each feature or bugfix gets its own branch, which is later merged back to main. This is ideal for small, trusted teams and private projects.

## Team Project: Create PR from your Branch
**Small Teams (All Have Write Access) – Branch-Based Workflow**
- Clone the main repository:
```
git clone https://github.com/your-org/project.git
cd project
```
- Create a new branch for your feature or fix:
```
git checkout -b feature/my-feature
```
- Or List all branches and switch to one of them, and rebase with the latest code for that feature branch.
```
git branch -a
git switch feature/new-feature   or  git checkout feature/new-feature  
git pull origin feature/new-feature
```
- Work on your changes, commit them:
```
git add .
git commit -m "Describe your change"
```
- Push your branch to the shared repository:
```
git push origin feature/my-feature
```
- Open a Pull Request (PR) from your branch to main. You have to go to Github webpage and your branch to create PR. After review, the PR is merged into main by a team member.
**Summary: Each team member creates branches in the same repo. Merges happen via PRs to main.**
- What Gets Merged?: Branches: Team members merge their feature branches into main (or a development branch) via PRs.

## Common Scenario: Verify Team Member’s PR
- While working together, how to fetch and check out a team member’s Pull Request (PR) locally, especially when you are already working on your feature branch.
```
git checkout feature/my-feature
git fetch origin pull/123/head:pr-123
git checkout pr-123
```
- `git checkout feature/my-feature`: Assume you are working on your own branch. Skip this step if you are on main and directly want to verify PR
- `git fetch origin pull/123/head:pr-123`: This command downloads the changes from PR #123 on the remote (origin) and creates a new local branch called pr-123 with those changes. It does not affect your branch.
- `git checkout pr-123`: This switches your working directory to the new local branch pr-123, so you can review, test, or work with the PR code.
- When Should You Use This?: When you want to review, test, or build upon Team Member’s PR before it’s merged.
- When you want to see the PR’s code in your local environment, possibly to help resolve conflicts or test integration with your own feature branch.


## Common Scenario: You Want to Combine Friend's PR with Your Feature Branch
- Make sure both branches are up to date, Check out your feature branch.
```
git fetch origin
git checkout feature/my-feature
```
- Merge the PR branch into your branch:
```
git merge pr-123
```
- Now your branch contains both your changes and the PR’s changes, Resolve any conflicts if prompted.

**Summary Table**
| Action | Command |
|--------|---------|
| Fetch PR #123 as a local branch | git fetch origin pull/123/head:pr-123 | 
| Switch to the PR branch | git checkout pr-123 |
| Merge PR branch into your feature branch	| git checkout feature/my-feature git merge pr-123 |

---
**Always create a new branch (not work directly on main) for each feature or fix and Merge changes to main via PRs**