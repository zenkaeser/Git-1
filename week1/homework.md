# Homework

In this exercise you will get some practice submitting your homework by pushing it to Github and then doing a pull request. Here are the instructions:

1. Start by creating a branch for your homework, named `git/week1`, and move to that branch
2. Inside the folder `hyf-homework/git/week1` create a new file named `my_favorite_food.txt`, inside the file write your favorite food recipe, and commit your changes (you can just find a random recipe on google and paste it in the file ;) ).
3. Again inside the folder `hyf-homework/git/week1` add a new file named `my_second_favorite_food.txt`, inside the file write the recipe for your second favorite food, and commit your changes.
4. Inside the folder `hyf-homework/git/week1` create a third file named `countries.txt`, where you list three countries that you have visited (this doesn't need to be true, you can just write the names of three random countries), and commit your changes.
5. Push your changes into your `hyf-homework` repository on github.
6. **On your computer** add a fourth country name to the file `countries.txt`, and commit your changes again.
7. **On github**, add also a fourth country name to the file `countries.txt`, and commit your changes there.
8. Push your local changes into your `hyf-homework` repository on github (and now it will not be that easy :) ).
9. Create a pull request from the branch `git/week1` to master
10. When the pull request is accepted, merge it
11. Once the pull request is merged with master, update your local master branch.


Commands that you will need:
 - `git branch <branch_name>` - to create a new branch named `<branch_name>`
 - `git checkout <branch_name>` - to move to a branch named `<branch_name>`
 - `git add <file_name>` - tell git to start tracking a file and to update what will be commited
 - `git commit -m "commit_message"` - commit (save) your changes
 - `git push origin <branch_name>` - push (upload) your changes in the branch named `<branch_name>` sto your github repository into the branch named `<branch_name>`.
 - `git pull origin <branch_name>` - pull (download) your changes from your github repository, in the branch named `<branch_name>`, into your local branch named `<branch_name>`


Useful git commands:
  - `git status` - this is your best friend when you are using git :)
  - `git branch` - to check which branches exist and in which one you are (you can also see where you are when you do `git status`)
  - `git log`
  - `git log --oneline`


Command line commands that might be useful:
 - `pwd`- print working directory, to know where you are 
 - `cd <folder_name>` - to go inside a folder named `<folder_name>` 
 - `cd ..`- to go to the parent folder of your current folder
 - `mkdir <folder_name>` - to create a new folder
 - `ls`- list all the folder contents
 - `ls .*` - list all the folder contents, also invisible folders/files (e.g. the git folder)
