# GIT Learnings

1. Git is a distributed version control system that tracks changes in any set of computer files.
2. Git is a distributed version control system, which means that a local clone of the project is a complete version control repository.
3. The git config command is used to set Git configuration values on a global or local project level. Common configuration settings like email, username, and editor can be set using git config command.
4. Configurations can be applied at local(--local), global(--global), and system(--system) level. By default, git config will write to a local level.
5. Local configuration values are stored in a file that can be found in the repo's .git directory: .git/config. Global configuration values are stored in a file that is located in a user's home directory. ~ /.gitconfig. The system level configuration file lives in a gitconfig file off the system root path. $(prefix)/etc/gitconfig on unix systems.
   git config --global user.email "your_email@example.com"
   git config --global core.editor "code --wait"
   git config --global user.name "your_name"
6. A Git repository is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed.
7. To create a new repo, you'll use the git init command. git init is a one-time command you use during the initial setup of a new repo. Executing this command will create a new .git subdirectory in your current working directory. This will also create a new main/master branch.
8. Git has three areas namely working directory, staging area and committed area.
9. Use "git status" command to see the untracked files. Use "git add 'file_name'" command to add the files to staging area. And finally use "git commit -m 'commit message'" to commit to repository.
10. We can use "git commit -am 'commit message'" to both add and commit at the same time. Use "git log" command to see the history of commits on a branch.
11. "git commit" command will commit all changes and open up default editor for providing the commit message.
12. HEAD always points to the current branch latest commit and we can see it under .git directory at ".git/HEAD". For each branch there will HEAD related files under .git/refs/heads/'branch_name'.
13. Another variation of "git log" is "git log --pretty".
14. Git basic workflow is work on changes, add changes to staging area, and then commit to repository.
15. Keep git commits as atomic as possible.
16. A .gitignore file ignores the specified pattern files from tracking. A line starting with # serves as a comment. prefix "!" which negates the pattern. The slash "/" is used as the directory separator. An asterisk "*" matches anything except a slash. The character "?" matches any one character except "/". Two consecutive asterisks ("**") in patterns matched against full pathname. To stop tracking a file that is currently tracked, use 'git rm --cached file_name' to remove the file from the index.
17. To amend an immediate commit use command "git commit --amend". sequence is git commit, then add forgotten files using git add, then git commit --amend.
18. In git default branch name is called master. In 2020, Github renamed the default branch from master to main. But Git still calls it master.
19. We can view all branches using "git branch" command. current branch is shown with an asterisk.
20. "git branch 'branch_name'" creates a new branch based on upon the current HEAD but it doesn't switch to that branch. To switch branches use command "git switch 'branch_name'". We can also use "git checkout 'branch_name'" to switch branches as well but it's legacy.
21. To create a branch and then switch immediately use the command "git switch -c 'branch_name'" or "git checkout -b 'branch_name'".
22. If we have un-committed changes which are common across branches then if we switch branches they'll follow to new branch.
23. Use "git branch -d 'branch_name'" to delete a branch. Switch to other branch before performing this operation. Use "git branch -D 'branch_name'" for force delete.
24. To rename a branch, switch to the branch and then use command "git branch -m 'new_branch_name'".

### Git merge
    
1. We merge branches, not specific commits. We always mege to the current HEAD branch.
2. To merge 2 branches, first switch to the receiving branch Ex. master/main/trunk and then run command "git merge 'feature_branch_name'". This will merge code from feature_branch_name to main/mater/trunk.
3. A fast-forward merge happens when master/main/trunk catches up with a feature branch by some commits assuming no commits happened on master branch after creating feature branch.
4. When master had commits after creating feature branch, and when we try merging both, a merge commit happens and git prompts for merge commit message in configured editor.
5. When a file is modified at the same place on two different  branches or when a file is modified on one branch but deleted in some other branch, in these cases when we try and merge these branches, there will be conflicts which git cannot resolve on its own.
6. Conflict Markers are used to highlight the problematic lines in code. Text between **<<<HEAD and ===** comes from recipient branch. Text between **=== and >>>** comes from merging branch.
7. Open up the files with conflicts, edit the files to remove conflicts, remove the conflict markers in the doc, then add and commit changes.

### Git diff
1. Without any additional options **git diff** lists all the changes in our working directory that are not staged for the next commit.
2. **git diff** is used generally to compare two same files.
3. Git declares one file as **A** and the other as **B**.
4. A diff shows only portions or chunks that were modified but also includes some unchanged lines before and after to provide context.
5. Each chunk starts with a chunk header found between **@@ and @@**. For example, @@ -3,4 +3,5 @@.
6. From file A, 4 lines are extracted starting from line 3. From file B, 5 lines are extracted starting from line 3.
7. Every line that changed between the 2 files is marked eith a + or - symbol.
8. Lines that begin with - come from file A and lines that begin with + come from file B.
9. git diff to see changes between working directory and staging area.
10. git diff HEAD to see changes between working directory, staging area and repository.
11. git diff -staged or --cached to see the difference between staging area and out last commit.
12. git diff --staged 'file_name' we can view the changes within a specific file by providing.
13. git diff branch1..branch2 compare two branches
14. git diff commit..commit compare two commits.

### Git Stash
1. Use **git stash** to temporarily stash/shelve changes made to working copy so that we can work on something else.
2. Commands related to stashing are **git stash**, **git stash list**, **git stash save**, **git statsh pop**, **git stash apply**, **git stash pop stash@{2}**, **git stash show**, **git stash drop stash@{1}**, and **git stash clear**.

### Git checkout
1. Use **git checkout** to checkout a particular commit by providing commit hash to it.
2. Now, we wiil be in detached HEAD mode. HEAD always points to a branch and Branch to latest commit. In detached HEAD mode, branch and HEAD will be in different places.
3. From the commit point we can start a new branch using **git switch -c 'branch_name**.
4. Another way to refer to previous commits is to use **git checkout HEAD~1** and similarly **HEAD~2** etc..
5. To switch back to previous branch simply use **git switch -**.
6. To revert the file back to whatever it looked like when last committed, we can use **git checkout HEAD 'filename'** to discard any changes in that file, reverting back to the HEAD.
7. Another option instead of using HEAD is substitute -- followed by the file(s) names like **git checkout -- 'file_name'**.
8. 


