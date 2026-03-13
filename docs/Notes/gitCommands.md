# Git Commands

## Basic Commands
1. Initializes a new Git repository in the current directory.
```console
git init
```

2. Creates a copy of a remote repository in a local directory.
```console
git clone [url]
```

3. Creates a copy of a local directory in remote repository when we push code.
```console
git remote add origin [url]
```

4. Displays the state of the working directory and staging area.
```console
git status
```

5. Stages a file for the next commit.
```console
git add [file] / .
```

6. To unstage a file.
```console
git restore --staged [file]
```

7. To Discard a unstaged file.
```console
git restore [file]
```

8. Commits the staged changes with a descriptive message.
```console
git commit -m "[message]"
```

9. Fetches and integrates changes from a remote repository into the current branch.
```console
git pull
```

10. Uploads local commits to a remote repository.
```console
git push
```

11. Usage: `git push origin master` This will push your local master branch to the master branch on the remote repository named origin.
```console
git push origin [branch-name]
```

12. Lists branches & show current branch.
```console
git branch
```

13. Creates a new branch.
```console
git branch [new-branch-name]
```

14. Deletes a branch.
```console
git branch -d [branch-name]
```

15. Renames a branch.
```console
git branch -M [new-branch-name]
```

16. Switches to the specified branch.
```console
git checkout [branch-name]
```

17. Merges changes from the specified branch into the current branch.
```console
git merge [branch-name]
```

18. Displays changes between commits, the working directory, and the staging area.
```console
git diff
```

19. Temporarily saves changes that are not yet ready to be committed.
```console
git stash
```

20. stash with message/name.
```console
git stash push -m "your message here"
```

21. To see a list of stashes you’ve made.
```console
git stash list
```
output
```console
$ git stash list
stash@{0}: WIP on Sachi: 2baf704 few changes in OldCabinPage
stash@{1}: WIP on Sachi: 2baf704 few changes in OldCabinPage
```

22. To apply the most recent stash and keep it in the stash list.
```console
git stash apply
```

23. To apply a specific stash and keep it in the stash list.
```console
git stash apply stash@{1}
```

24. To apply the most recent stash and remove it in the stash list.
```console
git stash pop
```

25. To apply a specific stash and remove it in the stash list.
```console
git stash pop stash@{1}
```

26. To remove a most recent stash from the list without applying it
```console
git stash drop
```

27. To remove a specific stash from the list without applying it.
```console
git stash drop stash@{1}
```

28. `To remove all stashes`
```console
git stash clear
```
</details>

## Configuration Commands

1. Sets the global username for commits.
```console
git config --global user.name "[name]"
```

2. Sets the global email for commits.
```console
git config --global user.email "[email]"
```

3. Sets the username for commits.
```console
git config user.name "[name]"
```

4. Sets the email for commits.
```console
git config user.email "[email]"
```

5. Lists all configuration settings.
```console
git config --list
```

## Remote Commands

1. Lists the remote repositories associated with the local repository.
```console
git remote -v
```

2. Adds a new remote repository.
```console
git remote add [name] [url]
```

3. Removes a remote repository.
```console
git remote remove [name]
```

## Advanced Commands

1. Shows the commit history.
```console
git log
```

2. Unstages a file from the staging area.
```console
git reset [file]
```

3. Resets the index and working directory to match the specified commit (destructive).
```console
git reset --hard
```

4. Creates a new commit that undoes the changes from a specified commit.
```console
git revert [commit]
```

5. Re-applies commits from the current branch onto another branch (often used to integrate changes from one branch into another).
```console
git rebase [branch-name]
```

6. Creates a new tag pointing to the current commit.
```console
git tag [tag-name]
```

## Other Commands

1. Shows Present Working Directory.
```console
pwd
```

2. Lists all the files & folders in the current directory.
```console
ls
```

3. Lists all the files & folders in the current directory including hidden files & folders.
```console
ls -a
```
</details>
