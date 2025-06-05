# 🧯 Git Troubleshooting Guide 

## 1. Detached HEAD  
- You checked out a commit, not a branch.  
- Fix: `git checkout <branch-name>` or create new branch: `git checkout -b <new-branch>`

## 2. Merge Conflicts  
- Fix conflicts in files, then:  
  `git add <file>`  
  `git commit`

## 3. Wrong Branch Commit  
- Move commits:  
  `git checkout <correct-branch>`  
  `git cherry-pick <commit-hash>`

## 4. Forgot to Stage Files  
- Stage missing files: `git add <file>`  
- Amend commit: `git commit --amend --no-edit`

## 5. Lost Local Changes  
- Check stash:  
  `git stash list`  
  `git stash apply`  
- Otherwise, changes may be lost.

## 6. Push Rejected  
- Pull first: `git pull --rebase`  
- Then push: `git push`

## 7. Large Files Error  
- Use Git LFS:  
  `git lfs install`  
  `git lfs track "<file-pattern>"`  
  `git add .gitattributes <files>`  
  `git commit -m "Track large files"`  
  `git push`

## 8. Undo Last Commit  
- Keep changes staged: `git reset --soft HEAD~1`  
- Unstage changes: `git reset HEAD~1`  
- Discard changes: `git reset --hard HEAD~1`
