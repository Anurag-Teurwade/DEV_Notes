# 🔀 Common Git Collaboration Workflows

## 1. Feature Branch Workflow
- Create a new branch for each feature or bug fix.
- Work independently on the feature branch.
- After completion, create a pull request (PR) to merge into the main branch.
- Code review and testing happen before merging.

## 2. Gitflow Workflow
- Uses multiple branches to manage releases and features:
  - **main**: production-ready code.
  - **develop**: integration branch for features.
  - **feature**: branches off develop for new features.
  - **release**: branches off develop for preparing a release.
  - **hotfix**: branches off main to quickly fix production bugs.
- Helps maintain a clear workflow for large projects.

## 3. Forking Workflow
- Fork the original repository to your own GitHub account.
- Clone your fork locally and create branches for your work.
- Push changes to your fork.
- Create a pull request from your fork to the original repository.
- Commonly used in open source contributions.

## 4. Rebase Workflow
- Instead of merging, use `git rebase` to move your feature branch on top of the latest main branch.
- Maintains a linear, clean commit history.
- Useful for keeping history readable, but use carefully to avoid rewriting shared commits.


