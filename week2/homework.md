# Homework

In this exercise you will get some practice creating branches, merging, pushing/pulling to Github, and creating a pull request. Here are the instructions:

1. Start by creating a branch for your homework, named `git/week2`, and move to that branch
2. Inside the folder `hyf-homework/git/week2` create a new file named `veggies.txt`, inside the file write the name of 5 veggies, one per line. Commit your changes.
3. Push the branch `git/week2` to github.
4. While on `git/week2`, create a branch named `feature/veggies` and move to that branch.
5. On the file `veggies.txt`, modify the name of the third veggie, and add two more veggies (one per line) at the end. Commit your changes.
6. On Github, go to branch `git/week2` and modify the name of the third veggie in the file  `veggies.txt`. Commit your changes.
7. Before pushing the branch `feature/veggies` to github, update it with the latest changes on branch `git/week2` (hint: pull that branch from github and merge it with `feature/veggies`).
8. Now that `feature/veggies` has been updated, push it to github and create a pull request to `git/week2`.
9. Wait for feedback, there will be one more task before merging :)



Commands that you will need: 
 - `git add <file_name>` - tell git to start tracking a file and to update what will be commited
 - `git commit -m "commit_message"` - commit (save) your changes
 - `git branch <branch_name>` - to create a new branch named `<branch_name>`
 - `git checkout <branch_name>` - to move to a branch named `<branch_name>`
 - `git merge <branch_name>` - to merge the branch named `<branch_name>` with the branch where you are.
 - `git push origin <branch_name>` - push (upload) your changes in your current branch to your github repository into the branch named `<branch_name>`.
 - `git pull origin <branch_name>` - pull (download) your changes from your github repository in the branch named `<branch_name>`, into your current local branch. 
 
 
 ***Note***
  For the sake of consistency (and to avoid mistakes), make sure that when you push you do it to a branch with the same name as the branch where you are, e.g. if you are on a branch named `my_homework` then push to a branch named `my_homework` by typing `git push origin my_homework`.
  
  When pulling, if you want to pull from a branch named, for instance `git_homework`, make sure that you are in a branch with the same name (`git_homework`) on your computer as well, and only then do `git pull origin <branch_name>`.


Other useful git commands:
 - `git status` - remember, it is your best friend, it tells you what is the state of your repository and sometimes what you should do.
 - `git branch` - this is your second best friend, it tells you in which branch you are (you can also see where you are when you do `git status`)
  - `git log` - see your commit history with all the details
  - `git log --oneline` - see your commit history in a single line.
