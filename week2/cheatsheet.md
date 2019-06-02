# Cheat sheet

Here are the commands we used in the class and their meaning.

Some mixed commands:

 - `git init` - start a new git repository in the folder where you are (always do `git status` before `git init` to make sure you are not inside a git repository already).
 - `git diff <branch_name>`  or `git diff <remote>/<branch_name>`- to see the difference between the branch where you are and `<branch_name>`. You must add `<remote>/` before `<branch_name>` only if the branch you want to compare with is a remote branch.
 - `git log` - shows the history of commits in the current branch. Also allows you to see if branches are synchronyzed.


Commands to deal with branches:

 - `git branch <branch_name>` - create a new branch `<branch_name>`.
 - `git checkout <branch_name>` - go to branch `<branch_name>`.
 - `git branch` - check which local branches you have and where you are (in green).
 - `git branch -a` - show both local and remote tracking branches.
 - `git branch -vv` - to see local tracking branches.
 - `git merge <branch_name>` - merges the branch `<branch_name>` into your current branch.
 - `git merge <remote>/<branch_name>` - merges the remote branch `<branch_name>` into your current branch.
 - `git branch -d <brach_name>` - delete the branch `<branch_name>`.


Commands to interact with Github:

 - `git clone <github_repository_url>` - clone a remote github repository.
 - `git remote add <remote> <github_repository_url>` - adds a link between your local repository and the remote github repository with the url `<github_repository_url>`. `<remote>` is typically either `origin` or `upstream`.
 - `git remote -v` - shows a list of remotes and respective URLs.
 - `git push  <remote> <branch_name>` - push your local changes in your current branch into the branch `<branch_name>` in the `<remote>` github repository.
 - `git fetch  <remote> <branch_name>` - gets all changes on <branch_name> in the `<remote>` github repository but does **not** merge them with your current branch.
 - `git pull origin <branch_name>` - gets all changes on <branch_name> in the `<remote>` and merges them with your current branch.


