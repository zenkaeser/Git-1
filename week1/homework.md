# Homework

The idea of this exercises is to practice what we learned during the class.
There are two parts: in the first one we will practice the basics of git and github, while in the second part we will practice working with branches and doing pull requests.

## Part 1

1. Go to https://github.com/HackYourFuture-CPH/hyf-homework and fork this repository. Now you should have the `hyf-homework` repository in your own github account.
2. Clone the `hyf-homework` repository from YOUR github account.
3. Inside the folder `git/week1` create a new file named `my_favorite_food.txt`, inside the file write your favorite food recipe, and commit your changes (you can just find a random recipe on google and paste it in the file :wink: ).
4. Again inside the folder `git/week1` add a new file named `my_second_favorite_food.txt`, inside the file write the recipe for your second favorite food, and commit your changes.
5. Inside the folder `git/week1` create a third file named `countries.txt` where you list three countries that you have visited (this does not need to be true, you can just write the names of three random countries), and commit your changes
6. Add a fourth country name to the file `countries.txt`, and commit your changes again.
7. Push your changes into your `hyf-homework` repository on github.


Commands that  you will need:
 - `git clone <repository_link>` - clone a github repository
 - `git add <file_name>` - tell git to start tracking a file and to update what will be commited
 - `git commit -m "commit_message"` - commit your changes
 - `git push origin master` - push your changes into your github repository into the branch master.

Useful git commands:
  - `git status`
  - `git log`
  - `git log --oneline`




## Part 2
In this part you will create your own local repository, use branches to make changes, solve a merge conflict, and once you merged your branches into master, you will create a repository with the same name on github and push your changes to github.

1. create folder `git_homework`
2. start a git repository inside the folder `git_homework`
2. create file `homework_file.txt`, add line "my homework"
3. add file `homework_file.txt` to repository and commit your changes
4. create branch `fix_something`
5. on branch `fix_something` add the line "fixing stuff" to your file and commit the change
6. go back to `master` and create another branch named `add_content`
7. on branch `add_content` add the line "adding content" to your file and commit the change
8. go back to `master`
9. merge `fix_something` with `master`
10. go to branch `add_content` and merge the branch `master` with it (there will probably be conflicts that you need to figure out)
11. go to branch `master` and merge the branch `add_content` with it
12. create a new github repository called `git_homework`
13. push your changes in the master branch into the github repository you just created.
14. post the link to your `git_homework` repository :slightly_smiling_face:


Git commands that you will need:
 - `git init` - create a new repository
 - `git add <file_name>` - tell git to start tracking a file and to update what will be commited
 - `git commit -m "commit_message"` - commit your changes
 - `git branch <branch_name>` - create a new branch
 - `git checkout <branch_name>` - go to branch `branch_name`
 - `git branch` - check which branches you have and where you are
 - `git push origin master` - push your local changes into the master branch of your github repository

Command line commands that might be useful:
 - `cd <folder_name>` - to go inside folder_name
 - `cd ..`- to go to the parent folder of your current folder
 - `mkdir <folder_name>` - to create a new folder
 - `ls`- list all the folder contents
 - `ls .*` - list all the folder contents, also invisible folders/files (e.g. the git folder)
