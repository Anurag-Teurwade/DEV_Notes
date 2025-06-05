# 💻 Git Commands Cheat Sheet

## Setup & Basics
- `git config --global user.name "Your Name"`
- `git config --global user.email "you@example.com"`
- `git init` — Initialize repository
- `git clone <url>` — Clone repo

## Working with Files
- `git status` — Check changes
- `git add <file>` — Stage changes
- `git commit -m "message"` — Commit changes
- `git push origin main` — Push to remote
- `git pull origin main` — Pull changes

## Branching & Merging
- `git branch` — List branches
- `git checkout -b feature` — Create/switch branch
- `git merge feature` — Merge branch
- `git stash` — Temporarily save changes

## Undo & Logs
- `git reset --soft HEAD~1` — Undo last commit
- `git revert <commit>` — Revert a commit
- `git log` — View commit history
- `git diff` — See changes

## Advanced
- `git rebase`
- `git cherry-pick <commit>`
- `git tag <tagname>`
