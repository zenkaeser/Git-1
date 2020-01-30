Tutorial for HackYourFuture Git basics :octocat:. 
This tutorial has 4 sections:

1. Command line interface (bash)
2. Git
3. Github
4. Checkout


Also you can watch the class recordings here:
 - [Git class part 1](https://drive.google.com/open?id=1FqDgCosYyTWGHDBXcMYeyh3DjP3CifeG)
 - [Git class part 2](https://drive.google.com/open?id=1eccuqGA88XR3XVy2b1RcosvQ5I_F_Dod)


You can take a look at some old videos I've made here:
 - [Git intro part 1](https://drive.google.com/open?id=1fubN-BDbdAAxcWxyUso7Pi-eLhWNzjdH)
 - [Git intro part 2](https://drive.google.com/open?id=17NMQ9EuS9Fo339noRQ-LBn4qwVRhKzGC)

These videos are a bit old and I might show slighly different things and explain them in different ways.


And the slides used in the class can be found [here](https://docs.google.com/presentation/d/1sR3er7alG-LXNadByoiNHlTiwhxrDgzlJaTt_GdTImY/edit?usp=sharing) (check out the speaker notes as well :) ).


# 1. Command line (bash)

We used the command line a lot, a few basic commands we need are:
 - `pwd` to find where we are, in which folder/directory.
 - `ls` to list all the contents in the current directory.
 - `cd <folder_name>` to change directory to `folder_name`.
 - `mkdir <folder_name>` to create a new folder/directory named `folder_name`.

Marco has also made a cool video with 10 important commands, which you can see [here](https://www.youtube.com/watch?v=kN1-tseJnt0&amp).

# 2. Git

## 2.1 What is Git

* [ ] Version Control (aka Revision control, source control)
* [ ] Distributed version control system, Linus Torvalds, 2005
* [ ] GIT: Global Information Tracker


## 2.2. Configuring Git

On your local machine, in the command line type:

```
git config --global user.email "email@email.com"
git config --global user.name "username"
```

Make sure that the email is the same you used for the github account.
You can run these commands again whenever you want to change the email or the user name.

To set the default text editor used by Git to vscode, you can run:

```
git config --global core.editor "code -w"
```

This command assumes you can start vscode from the command line by just typing `code`. On macOS this doesn't seem to work right out of the box, and you might want to check the top answer [here](https://stackoverflow.com/questions/29971053/how-to-open-visual-studio-code-from-the-command-line-on-osx) and follow the instructions there, or just ask your mentor to help you :)


## 2.3 Creating a repository on your computer

Create a new directory in your home directory or any other suitable location using:

```
mkdir git_example
```

Enter the directory:

```
cd git_example
```

and create a new git repository using:

```
git init
```

You can also create a repository on your local machine by cloning a remote repository with `git clone <URL>` command. This copies the repository from a remote machine (typically github) and initializes it on your machine. You can try to clone some public repositories on [github.com](www.github.com).

Before creating any repository make sure you are not inside a git repository already. This is very important!!! To do so type `git status`, if you get an error it means you are not inside a git repository and you can safely create a new one.


## 2.4 Workflow
 Working Directory -> Index -> Local 
 Your local repository consists of three "trees" maintained by git. The first one is your Working Directory (workspace) which holds the actual files. The second one is the Index which acts as a staging area, and finally the local repository itself which actually contains your commit history.


### 2.3.1 add and commit

The basic Git workflow consists of two steps.
First, you add files/changes (to the index/staging area) to be committed.

```
git add <file_name>
```

Second, you actually commit (save) your changes by doing:

```
git commit -m "Commit message"
```


# 3. GitHub:

## 3.1 What is GitHub

GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere. There are other platforms like Gitlab and Bitbucket.


## 3.2 Creating a repository

Using your GitHub account, create a repository to which you can add files. 
Name the repository `git_example`. Create a public repository and **do not** check the box to create a README file. 
After you create the repository, the URL of your web page would be something like https://github.com/martamatos/git_example. Replace `martamatos` with your username. If you append `.git` to this URL, you will get the name of your GitHub repository: https://github.com/martamatos/git_example.git


## 3.3 Connecting your local repository to the remote repository on Github

When you have an existing local repository (in your computer) that you want to connect to the repository you just created on Github, you need to run:

```
git remote add origin https://github.com/marta_matos/git_example.git
```

Here you are basically adding the connection to a remote repository named `origin`, where `origin` (in this case) stands for `https://github.com/marta_matos/git_example.git`.
To check if your local repository is connected to a remote repository (e.g. on Github) and what is the address of that repository you can always run:

```
git remote -v
```


## 3.4 Pushing changes

To send the contents of your local repository to your remote repository (on github), execute

```
git push origin master
```

However, this command will fail if there are changes in the remote repository that you do not have on your local machine yet. In that case you first need to get the changes from the remote repository to your local machine. To do so you do:

```
git pull origin master
```


## 3.5 Troubleshooting

You could encounter errors if you do not follow the exact procedure as described above.
```
error: failed to push some refs to 'git@github.com:myrepo.git'
```
Solution:
```
git pull origin master
```

or

```
fatal: refusing to merge unrelated histories
```
Solution:
```
git pull --allow-unrelated-histories
```

## 3.6 Generating the ssh keypair

If you don't want to insert your username and password every time you do `git pull` or `git push`, you can create an ssh keypair.


 For Windows MSysGit/GitBash command prompt use
```
$ ssh-keygen.exe -C "username@email.com" -t rsa
```


For Linux/MAC, use

```
$ ssh-keygen -C "username@email.com" -t rsa
```

Supply your Github email address instead of this fake one. 
Accept the default location storage (default file) for the keys. When prompted for a passphrase, make up one, and don't forget it! This is your private key, do not share it with anyone.
You will have id\\\_*rsa and id\\\_rsa.pub files in the directory at the following path /c/Users/<your_user_name>/.ssh/

 You want to copy the contents of the id\_rsa.pub (open it with a simple text editor or use the command cat in the command line).  After you copy the contents of the id\_rsa.pub file, go to the GitHub account, go to the settings find SSH and GPG keys option and add New SSH key.


# 4. Checkout

We didn't talk about this in class, but it's kind of nice to know.
To move around a repository, to different branches or commits, you can use the `git checkout` command.

 When you do `git log` you see the history of all commits in the branch where you are. The first line of each commit looks like `commit fe48414f5c9a21c986ae3c65f198d477a81299cc`, where the weird sequence of numbers and letters is the commit hash key. If you  want to go to a particular commit all you need to do is:

```
git checkout <commit_hash_key>
```

At that point you can take a look around and see what your code looked like. 
Do **not** commit any changes when are in that state, it will probably get you into trouble :)

To return to the latest commit you do:

```
git checkout <branch_name>
```

Where `branch_name` is the name of the branch where you are.