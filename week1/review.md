Tutorial for HackYourFuture Git basics :octocat:. This tutorial has five sections:

1. Command line interface (bash)
2. Git
3. GitHub
4. Git branches
5. Others

Also you can watch the following videos that summarize the class contents:
 - [Git intro part 1](https://drive.google.com/open?id=1fubN-BDbdAAxcWxyUso7Pi-eLhWNzjdH)
 - [Git intro part 2](https://drive.google.com/open?id=17NMQ9EuS9Fo339noRQ-LBn4qwVRhKzGC)
 - [Git intro part 3](https://drive.google.com/open?id=1k8edrup6PEyPpuJG_6bRVXSTUlghUVSs)

# 1. Command line (bash)

We will be using the command line the whole class, a few basic commands we will need are:
 - `pwd` to find where we are, in which folder/directory.
 - `ls` to list all the contents in the current directory.
 - `cd <folder_name>` to change directory to `folder_name`.
 - `mkdir <folder_name>` to create a new folder/directory named `folder_name`.

Marco has also made a cool video with 10 important commands, which you can see [here](https://www.youtube.com/watch?v=kN1-tseJnt0&amp=&t=90s).

## 1.1 Vim

During the class we also use Vim, which is a command line text editor.
Vim has two modes: the command mode and the insert mode. To edit the file contents we  need to be in insert mode. To switch to insert mode we press `i`, and we should see `-- INSERT --` written in the bottom left corner. To save and/or exit, do searches, etc., we need to be in command mode. To switch to command mode we press `ESC`.
To save our changes and exit we go to command mode and type `:wq`, which stands for write and quit. We should see the text in the bottom left corner. To exit vim without saving our changes, we type `:q` while in command mode.

# 2. Git

## 2.1 What is Git

* [ ] Version Control (aka Revision control, source control)
* [ ] Distributed version control system, Linus Torvalds, 2005
* [ ] GIT: Global Information Tracker


## 2.2 Creating a repository

Create a new directory in your home directory or any other suitable location using
```
$ mkdir hello_world
```

Enter it
```
$ cd hello_world
```
and create a new git repository using
```
$ git init
```

You can also create a repository on your local machine by cloning a remote repository with `git clone <URL>` command. This copies the repository from a remote machine (typically github) and initializes it on your machine. You can try to clone some public repositories on [github.com](www.github.com).

Before creating any repository make sure you are not inside a git repository already. This is very important!!! To do so type `git status`, if you get an error it means you are not inside a git repository and you can safely create a new one.


## 2.3 Workflow
 Working Directory -> Index -> HEAD
 Your local repository consists of three "trees" maintained by git. The first one is your Working Directory which holds the actual files. The second one is the Index which acts as a staging area and finally the HEAD which points to the last commit you've made.


### 2.3.1 add and commit

The basic Git workflow consists of two steps.
First, you add files/changes (to the Index) to be committed.
```
$ git add <file_name>
```

Second, you actually commit your changes by doing:

```
$ git commit -m "Commit message"
```

# 3. GitHub:

## 3.1 What is GitHub

GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.


## 3.2 Configure your email and username

On your local machine, in the command line type:

 ```
$ git config --global user.email "email@email.com"
$ git config --global user.name "username"
```

Make sure that the username and email are the ones you used for the github account.


## 3.3 Creating a repository

Using your GitHub account, create a repository to which you can add files. Name the repository `my_first_repo`. Create a public repository and check the box to create a README file. After you create the repository, the URL of your web page would be something like https://github.com/martamatos/my_first_repo. Replace `martamatos` with your username. If you append .git to this URL, you will get the name of your GitHub repository: https://github.com/martamatos/my_first_repo.git


## 3.4 Pushing changes

If you have not cloned (our case) an existing repository and want to connect your repository to a remote server, you need to add it with

```
$ git remote add origin https://github.com/marta_matos/my_first_repo.git
```

Replace the URL with the repository you created in step 3.3

Now you are able to push your changes to the selected remote server i.e. your remote repository on GitHub.
Your changes are now in the HEAD of your local working copy. To send those changes to your remote repository, execute

```
$ git push origin master
```

However, this command will fail if there are changes in the remote repository that you do not have on your local machine. In that case you first need to get the changes from the remote repository to your local machine. To do so you do:

```
$ git pull origin master
```

As a best practice, you should always do this before you push any changes into the remote repository.

If instead of getting the new changes from the remote repository into your local machine you just want to know if there are any changes, you can do

```
$ git fetch origin master
```

Then if you do `git status` it will tell you whether or not your local repository is up-to-date with the remote repository.


# Troubleshooting

You could encounter errors if you do not follow the exact procedure as described above.
```
error: failed to push some refs to 'git@github.com:myrepo.git'
```
Solution:
```
$ git pull origin master
```

or

```
fatal: refusing to merge unrelated histories
```
Solution:
```
$ git pull --allow-unrelated-histories
```

## 3.4 Generating the ssh keypair

If you don't wat to insert your username and password every time you do `git pull` or `git push`, you can create an ssh keypair.


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


# 4 Branches

## 4.1 Why Branches ?

To expand.
Trees need branches to expand.
Banks needs (office) branches to expand.
Company needs (code) branches to expand.
E.g. Branches for Bugs, testing, featuers, production, staging etc.

## 4.2 What is remote ?

Before diving straight into Git branches, let's just clarify what is a remote.
If you're using Git collaboratively, you'll probably need to sync your commits with other machines or locations. In Git terminology, each machine or location is called a remote, and each one may have one or more branches. Most often, you'll just have one remote, named origin.

To list all the remotes, run
```
$ git remote
```

 To see which locations these remote names are shortcuts for, run
```
 $ git remote -v
 origin    https://github.com/unmeshvrije/leetcode
 origin    https://github.com/unmeshvrije/leetcode
```

## 4.3 Types of Branches

On your local machine, you've got three types of branches:
 1. local branches : non-tracking
 2. local branches : tracking
 3. remote-tracking branches

On a remote machine, you have just one type of branch

## Types of Branches (1) Branches on your machine:

### 4.3.1 Local branches

 To view a list of all the local branches on your machine, run
```
$ git branch
 master
 new-feature
```

There are two types of local branches on your machine: non-tracking local branches, and tracking local branches.


#### 4.3.1.1 Non-tracking local branches

  Non-tracking local branches are not associated with any other branch in the remote repository. To create one, run

```
$ git branch <branch_name>
```


####  4.3.1.2 Tracking local branches

Tracking local branches are associated with another branch on the remote repository, usually a remote-tracking branch. To create one, run

```
$ git branch --track <branch_name> [<start-point>]
```

To view which one of your local branches are tracking branches, run

```
  $ git branch -vv
  master      b31f87c85 [origin/master] "my sample commit"
  new-feature b760e04ed "my branch is strong"
```

From this command's output, you can see that the local branch master is tracking the remote-tracking branch origin/master, and the local branch new-feature is not tracking anything.

"Tracking local branches" are useful. They allow you to run `git pull` and `git push` without specifying which upstream branch to use. If the branch is not set up to track another branch, you'll get an error like this one:

```
  $ git checkout new-feature
  $ git pull
  There is no tracking information for the current branch.
  Please specify which branch you want to merge with.
  See git-pull(1) for details
  $ git pull <remote> <branch>
```

If you wish to set tracking information for this branch you can do so with:

```
$git branch --set-upstream new-feature <remote>/<branch>
```

###  4.3.2 Remote-tracking branches (still on your machine)

To view a list of all the remote-tracking branches on your machine, run

```
  $ git branch -r
  bitbucket/master
  origin/master
  origin/new-branch
```

Think of your remote-tracking branches as your local cache for what the remote machines contain. You can update your remote-tracking branches using `git fetch`, which `git pull` uses behind the scenes.
Even though all the data for a remote-tracking branch is stored locally on your machine (like a cache), it's still never called a local branch. (At least, I wouldn't call it that!). It's just called a remote-tracking branch.


##  4.3.3 Branches on a remote machine

To view all the remote branches (that is, the branches on the remote machine), run

```
    $ git remote show origin
    *remote origin
    Fetch URL: git@github.com:Flimm/example.git
    Push  URL: git@github.com:Flimm/example.git
    HEAD branch: master
    Remote branches:
    io-socket-ip            new (next fetch will store in remotes/origin)
    master                  tracked
    new-branch              tracked
    Local ref configured for 'git pull':
    master     merges with remote master
    new-branch merges with remote new-branch
    Local ref configured for 'git push':
    master     pushes to master     (up to date)
    new-branch pushes to new-branch (fast-forwardable)
```

This git remote command queries the remote machine over the network about its branches. It does not update the remote-tracking branches on your local machine, use `git fetch` or `git pull` for that.
From the output, you can see all the branches that exist on the remote machine by looking under the heading "Remote branches" (ignore lines marked as "stale").


# 5. Others

## 5.1 Checkout

The git checkout command lets you navigate between the branches created by git branch. Checking out a branch updates the files in the working directory to match the version stored in that branch, and it tells Git to record all new commits on that branch. Think of it as a way to select which line of development you’re working on.

To checkout the specified branch, which should have already been created with git branch, run:

```
git checkout <existing_branch>
```

This makes `<existing_branch>` the current branch, and updates the working directory to match.

To create a new branch and checkout <new_branch>, run
```
git checkout -b <new_branch>
```

The `-b`option is a convenience flag that tells Git to run `git branch <new_branch>` before running `git checkout <new_branch>`.


The checkout command can also be used to go to different commits. When you do `git log` you see the history of all commits in the branch where you are. The first line of each commit looks like `commit fe48414f5c9a21c986ae3c65f198d477a81299cc`, where the weird sequence of numbers and letters is the commit hash key. If you  want to go to a particular commit all you need to do is

```
$ git checkout <commit_hash_key>
```

To return to the latest commit you do

```
$ git checkout <branch_name>
```

Where `branch_name` is the name of the branch where you are.


## 5.2 HEAD in Git

HEAD points to the tip of the "current branch". When you switch branches with git checkout, the HEAD revision changes to point to the tip of the new branch.
To see where the HEAD is pointing, run:

```
cat .git/HEAD

```

In my case, the output is:

```
$ cat .git/HEAD
ref: refs/heads/master
```

It is possible for HEAD to refer to a specific revision that is not associated with a branch name. This situation is called a detached HEAD.
