# Part I

### 1. What is the difference between git reset and git revert. When would you use one over the other?
### ans: Both undo commits but git reset removes the commits from the commit history while git revert appends a new commit with the resulting content. Git revert is preferred when working with a team of other developers

### 2. What is the difference between git merge and git rebase. When would you use one over the other?
### ans: Git merge creates a new commit that consists of changes of all commits on both branches at that instance, while git rebase simply moves the entire second branch to the tip of the current branch, thereby incorporating all commits in the current branch. Git merge is preferred when working with public branches (branches used by others)

### 3. What is the difference between git stash pop and git stash apply. When would you use one over the other?
### ans: Both remove the latest stashed change back to the working directory but git stash pop removes it from the list while git stash apply keeps it on the list. Git stash apply is preferred if stash may still be referrenced later

### 4. What kinds of things can you do in interactive mode when rebasing?
### ans: One can alter the commits as they are moved to the new branch.