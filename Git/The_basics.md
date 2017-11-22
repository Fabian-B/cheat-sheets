# Starting a new repository
1. Navigate to the folder on you system that will contain the staging area
2. Open git bash and type ```git init``` to create a new repository
3. With ```git add [filename]``` add every file you want to the staging area
4. Commit it to the repository with an appropriate message typing ```git commit -m "your message goes here"```
5. Finally push all commits to the repository ```git push```

# Clone an existing repository to your system
Type ```git clone [repository https URL]```

# Basic git operations
* Check the differences between the working directory and the staging area with: ```git diff [filename]```
* Commits are stored chronologically in the repository and can be viewed with: ```git log```
* In Git, the commit you are currently on is known as the HEAD commit. In many cases, the most recently made commit is the HEAD commit.
To see the HEAD commit, enter: ```git show HEAD```
* Restore a file in your working directory to look exactly as it did when you last made a commit: ```git checkout HEAD [filename] ```
* Resets the file in the staging area to be the same as the HEAD commit. In other words undo an ```git add``` action.
* The first 7 characters of the SHA of a previous commit can be used to reset back to that commit. To do this type: ```git reset commit_SHA```


# The Git branch workflow.
* ```git branch```: Lists all a Git project's branches.
* ```git branch branch_name```: Creates a new branch.
* ```git checkout branch_name```: Used to switch from one branch to another.
* ```git merge branch_name```: Used to join file changes from one branch to another.
* ```git branch -d branch_name```: Deletes the branch specified.

