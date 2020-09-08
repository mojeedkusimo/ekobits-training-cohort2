# Part I

### 1. What does git clean do?
### ans: It removes files not tracked by git

### 2. What do the -d and -f flags for git clean do?
### ans: The -d flag ensures recursive removal of directories, while the -f forces git clean to delete the files incase git configuration variable, clean.requireForce is set to true. 

### 3. What git command creates a branch?
### ans: git branch NAME_OF_BRANCH 

### 4. What is the difference between a fast-forward and recursive merge?
### ans: The fast-forward merge occurs when git can aesily detect the chronological order in which commits were made and simply fast-forwards the commit behind to the one ahead while the recursive merge when the order in which commits were made is unknown.

### 5. What git command changes to another branch?
### ans: git checkout NAME_OF_BRANCH

### 6. How do you remove modified or deleted files from the working directory?
### ans: git checkout FILENAME

### 7. What git command deletes a branch?
### ans: git branch -D NAME_OF_BRANCH

### 8. What does the git diff command do?
### ans: This command alone allows us see changes in the working tree not yet staged for the next commit, however, when used with other options (commit/branch), it allows compare the current location/status with that option.

### 9. How do you remove files from the staging area?
### ans: git reset --mixed SHA_OF_COMMIT

### 10. How do merge conflicts happen?
### ans: This occurs when changes are commited to thesame file on two different branches.

# Part II

### Create your own merge conflict! Work on the same file on two separate branches and merge the two branches together. Fix the conflicts and finish your merge. In the real world you will never intentionally try to create merge conflicts, but it is important to understand how and why they are created. Most importantly, it's important not to be intimidated by merge conflicts, and to be able to fix them with confidence!

### ans: find screenshots here: [before](/git-and-github/branching-and-merging-screenshots/branching-and-merging-solution-part2-before.png) and [after](/git-and-github/branching-and-merging-screenshots/branching-and-merging-solution-part2-after.png)