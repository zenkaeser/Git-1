# Cheat sheet

Here are the commands we used in the class and their meaning.

## Command line
 - `pwd` - stands for 'print working directory' and you use it to know in which directory you are.
 - `cd <folder_name>` - stands for 'change directory', and you use it to go inside `folder_name`.
 - `cd ..` - to go to the parent folder of your current folder.
 - `mkdir <folder_name>` - stands for 'make directory' and you use it to create a new folder with `folder name`.
 - `ls` - stands for 'list' and you use it list all the folder contents.
 - `ls .*` - list all the folder contents, also invisible folders/files (e.g. the .git folder).
 - `rm <file_name>` - THIS IS DANGEROUS!!! It removes the file named `file_name` FOREVER, you can NEVER recover it.
 
To remove a git repository but still keep your files do `rm -rf .git` in the folder where you have the repository. All the git information is lost when you do this.

## Git 

### Part 1

We used these commands in the first part of the class to work with a local git repository on our own computers.

 - `git init` - start a new git repository in the folder where you are (always do `git status` before `git init` to make sure you are not inside a git repository already).
 - `git add <file_name>` - tells git to start tracking a file or to update what will be commited. Always do that before `git commit`.
 - `git commit -m "commit_message"` - commit your changes.
 - `git status` - shows you which files are ready to be commited, or not tracked by git. Often tells you what to do as well.
 - `git log` - shows the history of commits in the current branch.
 - `git log --oneline` - shows the history of commits in the current branch in a single line per commit.
 
 Note: if you do `git add .` instead of `git add <file_name>` you will add all files in your current folder.
 
 
 ### Part 2
 
 We used these commands in the second part of the class to link our local git repository to a remote git repository (on Github) and work with it.

 - `git clone <github_repository_url>` - clone a github repository with url `github_repository_url`. 
 - `git remote add origin <github_repository_url>` - adds a link between your local repository and the github repository with the url `github_repository_url`.
 - `git remote -v` - shows the url of the github repository to which your local repository is linked.
 - `git push origin <branch_name>` - push your local changes in your current branch into the branch named `branch_name` in your github repository. In the class `branch_name` was `master`.
 - `git pull origin <branch_name>` - get all remote changes from the branch named `branch_name` in the github repository to your local repository. In the class `branch_name` was `master`.


In the beginning it is a good idea to do `git status` before `git clone <repository_link>` to make sure you are not inside a git repository, and do `git remote -v` after `git clone <repository_link>` to make sure you cloned the right repository.


### Part 3

We used these commands in the third part of the class to work with branches.

 - `git branch <branch_name>` - create a new branch named `branch_name`.
 - `git checkout <branch_name>` - go to branch `branch_name`.
 - `git branch` - check which branches you have and where you are (in green).
 - `git merge <branch_name>` - merges the branch named `branch_name` into your current branch.
 - `git branch -d <brach_name>` - delete the branch named `branch_name`.


### Part 4

Other commands that we talked about in class.
 
 - `git checkout --file <file_name>` - use if you changed the file named `file_name` and want to revert the changes, i.e. to get back the version you had in the last commit 
 - `git checkout <commit>` - use to go to a previous commit. Commit stands for the weird code you see in yellow when you do `git log` (e.g. 7c9025846b37410bb0e35ac7333b3cfa78aca5e7). To go back to your latest commit do `git checkout <branch_name>`, where the branch name is the branch where you are.


### Part 5

Commands that we did not talk about in class but that might be useful. 

 - `git diff <file_name>` - to see the difference between the file contents now and in the latest commit.
 - `git rm <file_name>` - THIS IS DANGEROUS!!! Removes the file from both working directory and git.
 - `git rm --cached <file_name>` - to remove the file from git tracking, but still keep it in the working directory.
 
 
To draw all the branches in the terminal:

 - `git log --all --graph --decorate --oneline`
 - `git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all`
 
