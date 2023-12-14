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
17.    
