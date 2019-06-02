# Homework

The idea of this homework is to practice the forking workflow that we learned in class. We will be basically repeating the last exercise we did in class.

The general idea of the forking workflow is that there is a Github repository that you want to contribute to but you don't have permissions to do it. Let's imagine this repository you want to contribute to is the `vscode` repository on microsoft's github account.

So what you do is to fork that repository, `microsoft/vscode`, which means you copy the repository to your own account, and now you have `yourusername/vscode`. Then you clone `yourusername/vscode` (the `vscode` repository in your github account) to your computer, which means you copy the repository in your github account to your computer.

Once you have the repository cloned in your computer, you create a branch where you do all the changes you want to do (and do quite a few commits in the meantime), and then you want to merge that branch with `master` (or any other branch) on `microsoft/vscode`, but again you don't have permissions to do it. So, first you push the branch where you did the changes to `yourusername/vscode` and then you go to github and do a pull request from your branch on `yourusername/vscode` to `master` in the repository `microsoft/vscode`.

One important thing though is that, before you push your branch to github and do the pull request, you must add any changes that might have been made in the `master` branch in `microsoft/vscode` to your own branch where you did all the changes. To do so you must add a remote for `microsoft/vscode` (upstream) to your local repository, fetch the changes from the branch `master` in the upstream repository, and merge these changes with your local master and your own branch where you did all the changes. And then you are ready to push to `yourusername/vscode` and do the pull request.

And [here](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) is also a nice article about the forking workflow.

Some terminology to consider:
 - `origin` in general refers to `yourusername/vscode` in the example above;
 - `upstream` in general refers to `microsoft/vscode` in the example above;
 - `origin/branch_name`  refers to `branch_name` in the `origin` remote (github repository);
 - `upstream/branch_name`  refers to `branch_name` in the `upstream` remote (github repository);


Below are the homework instructions, they are not super detailed though, because I want you to think about what you are doing and not just type :)


1. fork this repository: `https://github.com/martamatos/git_advanced_class_homework.git`;
2. clone your forked repository into your computer;
3. create a branch `add_division` and go to it;
4. in the file `math.js` add a function to divide two numbers at the end of the file. the function should take two numbers as arguments (e.g., `a` and `b`) and return the result of their division (e.g. `a/b`). Commit your changes;
5. add MY repository remote as upstream (`git remote add <remote> <URL>`);
6. check for changes in `upstream/master` and integrate them with both your local `master` branch and your local `add_division` branch (I will be checking this!);
7. push `add_division` to YOUR github repo;
8. do a pull request to my repository;

Remember to write meaningful commit messages and to give a meaningful title to the pull request ;)




