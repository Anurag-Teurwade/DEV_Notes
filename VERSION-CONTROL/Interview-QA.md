# 🧪 Git & GitHub Interview Questions & Answers

1. What is Git?  
   Git is a distributed version control system used to track changes in source code during software development.

2. What is GitHub?  
   GitHub is a web-based hosting service for Git repositories that provides collaboration features like issue tracking, pull requests, and code review.

3. What is the difference between Git and GitHub?  
   Git is a version control tool; GitHub is a platform that hosts Git repositories and adds collaboration features.

4. What is a commit?  
   A commit is a snapshot of changes saved in the Git repository, representing a point in the project history.

5. What is branching in Git?  
   Branching allows you to create separate lines of development, enabling multiple features or fixes to be worked on simultaneously.

6. How do you create a new branch?  
   `git branch <branch-name>`

7. How do you switch to a branch?  
   `git checkout <branch-name>`

8. What is the difference between `git fetch` and `git pull`?  
   `git fetch` downloads updates from a remote repository without merging, while `git pull` downloads and merges those updates automatically.

9. What is merging?  
   Merging is the process of combining changes from one branch into another.

10. What is a pull request?  
    A pull request is a GitHub feature where you request to merge your code changes into another branch, typically after review.

11. What is a remote repository?  
    A remote repository is a version of your project hosted on the internet or network (e.g., GitHub).

12. How do you clone a repository?  
    `git clone <repository-url>`

13. What does `git status` show?  
    It displays the state of the working directory and staging area, showing changes to be committed or untracked files.

14. What is the staging area?  
    The staging area (index) is where you prepare changes to be included in the next commit.

15. How do you add files to the staging area?  
    `git add <file-name>` or `git add .` to add all changes.

16. How do you commit changes?  
    `git commit -m "commit message"`

17. What is a commit hash?  
    A unique SHA-1 hash identifier for each commit.

18. How do you see commit history?  
    `git log`

19. What is `git diff` used for?  
    Shows the differences between files or commits.

20. How do you delete a branch?  
    `git branch -d <branch-name>`

21. What is the difference between `git merge` and `git rebase`?  
    `merge` combines histories creating a merge commit; `rebase` rewrites commit history for a linear sequence.

22. How do you undo a commit that hasn’t been pushed?  
    `git reset --soft HEAD~1`

23. How do you undo a commit that has been pushed?  
    Use `git revert <commit-hash>` to create a new commit that undoes the changes.

24. What is a tag in Git?  
    A tag marks specific points in history as important (e.g., release versions).

25. How do you create a tag?  
    `git tag <tag-name>`

26. How do you push tags to a remote?  
    `git push origin <tag-name>`

27. How to resolve merge conflicts?  
    Manually edit conflicted files, then stage and commit the changes.

28. What is the `.gitignore` file?  
    A file specifying intentionally untracked files Git should ignore.

29. How do you see all branches, including remote?  
    `git branch -a`

30. What is `git stash`?  
    Temporarily saves changes you don’t want to commit yet, allowing you to switch branches cleanly.

31. How do you apply stashed changes?  
    `git stash apply`

32. How do you delete a stash?  
    `git stash drop`

33. What does `git remote -v` do?  
    Lists the remote repositories and their URLs.

34. How do you rename a branch?  
    `git branch -m <new-branch-name>`

35. What is a bare repository?  
    A repository without a working directory, used mainly for sharing.

36. How to check Git version?  
    `git --version`

37. How do you configure your username and email in Git?  
    ```
    git config --global user.name "Your Name"
    git config --global user.email "your.email@example.com"
    ```

38. What is fast-forward merge?  
    A merge where the branch pointer is simply moved forward because no divergent changes exist.

39. How to discard local changes in a file?  
    `git checkout -- <file-name>`

40. How do you show the differences between branches?  
    `git diff <branch1>..<branch2>`

41. What is the default branch name in Git?  
    `main` (formerly `master`)

42. How to see untracked files?  
    `git status`

43. How to rename a file in Git?  
    `git mv <old-name> <new-name>`

44. What is the difference between `git reset` and `git revert`?  
    `reset` changes commit history (can be destructive); `revert` creates a new commit to undo changes safely.

45. What is a detached HEAD?  
    A state where HEAD points directly to a commit, not a branch.

46. How do you create a new repository on GitHub?  
    Use GitHub UI or CLI tools like `gh repo create`.

47. How to clone a private repository?  
    Use SSH or HTTPS with authentication.

48. What is GitHub Actions?  
    A CI/CD platform to automate workflows.

49. How do you squash commits?  
    Using interactive rebase: `git rebase -i HEAD~n`

50. How do you check changes staged for commit?  
    `git diff --cached`

