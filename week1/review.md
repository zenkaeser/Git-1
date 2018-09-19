Tutorial for HackYourFuture Git basics :octocat:. This tutorial has three sections:
1. Git
2. GitHub
3. Using Git

# 1. Git : 

## 1.1 What is Git, Etymology and a short history.
* [ ] Version Control (aka Revision control, source control)
* [ ] Distributed version control system, Linus Torvalds, 2005
* [ ] GIT: Global Information Tracker

## 1.2 Installing Git
 For Windows,
 install Git for Windows:
 https://github.com/git-for-windows/git/releases/tag/v2.10.2.windows.1

 For Linux, open gnome-terminal for GNome desktops  or Konsole for KDE desktops and type the command to install git based on your Linux distribution. 

 For a RedHat based Linux (Like CEntOS)
```
 sudo yum install git
```

 For Fedora
```
 sudo yum install git-core
```

 For a Debian based Linux (like Ubuntu)
```
 sudo apt-get install git 
```

 For Arch Linux
```
 sudo paceman -Sy git
```

 For Gentoo Linux
```
 sudo emerge ask —verbose dev-util/git
```

 For a MAC, open Terminal and execute following command
```
 brew install git
```

# 2. GitHub: 

## 2.1 What is GitHub 
 GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

 Registering/Creating the account on GitHub
 You need
* A valid Email address
* An SSH key-pair


## 2.2 Generating the ssh keypair

 For Windows MSysGit/GitBash command prompt use
```
ssh-keygen.exe -C "username@email.com" -t rsa
```

```
 For Linux/MAC, use
ssh-keygen -C "username@email.com" -t rsa
```

Supply your Github email address instead of this fake one. 
Accept the default location storage (default file) for the keys. When prompted for a passphrase, make up one, and don't forget it ! This is your private key, do not share it with anyone.
You will have id\\\_*rsa and id\\\_rsa.pub files in the directory at the following path /c/Users/<your_user_name>/.ssh/

 You want to copy the contents of the id\_rsa.pub (open it with a simple text editor or use the command cat in the Bash)
 After you copy the contents of the id\_rsa.pub file, Go to the GitHub account, go to the settings find SSH and GPG keys option and add New SSH key.

## 2.3 Creating a repository

Using your GitHub account, create a repository to which you can add files. Name the repository as MyFirst. Create a public repository and check the box to create a README file. After you create the repository, the URL of your web page would be something like https://github.com/unmeshvrije/MyFirst . Replace unmeshvrije with your username. If you append .git to this URL, you will get the name of your GitHub repository: https://github.com/unmeshvrije/MyFirst.git



# 3. Using Git

## 3.1 Creating the repository
```
Create a new directory in your home directory or any other suitable location using
$mkdir hello-world
Enter it
$cd hello-world
and create a new git repository using 
$git init
```

You can clone a repository with `git clone <URL>` command. This copies the repository from a remote machine and initializes it on your machine. You can try to clone some public repositories on github.com

Need some more explanation? Than check out [this](https://www.youtube.com/watch?v=4xDSfNTi3p4&list=PLVYDhqbgYpYUGxRdtQdYVE5Q8h3bt6SIA) video Daan made about how to set up a new Git repo 

## 3.2 Workflow
 Working Directory -> Index -> HEAD
 your local repository consists of three "trees" maintained by git. the first one is your Working Directory which holds the actual files. the second one is the Index which acts as a staging area and finally the HEAD which points to the last commit you've made.

 configure your email and username of Github in the git
 ```
$git config --global user.email "username@email.com"
$git config --global user.name "username"
```

 Make sure that the username is the one you used for the github account.

## 3.3 add and commit
```
 #You can propose changes (add it to the Index) using
 $git add <filename>
 #This is the first step in the basic git workflow.
 
 #To actually commit these changes use
 $git commit -m "Commit message"
```

## 3.4 Pushing changes
```
#If you have not cloned (Our case) an existing repository and want to connect your repository to a remote server, you need to add it with

$git remote add origin https://github.com/unmeshvrije/MyFirst.git
Replace the URL with the repository you created in step 2.3

 Now you are able to push your changes to the selected remote server i.e. your remote repository on GitHub.
 Your changes are now in the HEAD of your local working copy. To send those changes to your remote repository, execute 
 $git push -u origin master
```
# Troubleshooting
You could encounter errors if you do not follow the exact procedure as described above.
```
error: failed to push some refs to 'git@github.com:myrepo.git'

Solution:

$ git pull origin master
```

```
fatal: refusing to merge unrelated histories

Solution:

$ git pull --allow-unrelated-histories
```



This tutorial has three sections: (1) Branches (2) Checkout (3) HEAD


# Branches

## Why Branches ?
To expand.
Trees need branches to expand. 
Banks needs (office) branches to expand.
Company needs (code) branches to expand.
E.g. Branches for Bugs, testing, featuers, production, staging etc. 

## What is remote ?

If you're using Git collaboratively, you'll probably need to sync your commits with other machines or locations. In Git terminology, each machine or location is called a remote, and each one may have one or more branches. Most often, you'll just have one, named origin.
To list all the remotes, run
`$ git remote`

 To see which locations these remote names are shortcuts for, run
```
 $ git remote -v
 origin    https://github.com/unmeshvrije/leetcode
 origin    https://github.com/unmeshvrije/leetcode

 Each remote has a directory under git/refs/remotes/:
 $ ls -F .git/refs/remotes/
```

## Types of Branches

On your local machine, you've got three types of branches:
 1. local branches : non-tracking
 2. local branches : tracking
 3. remote-tracking branches

On a remote machine, you have just one type of branch

## Types of Branches (1) Branches on your machine:

### 1.1 Local branches 

 To view a list of all the local branches on your machine, run
```
$ git branch
 master
 new-feature

 Each local branch has a file under .git/refs/heads/:
 $ ls -F .git/refs/heads/
 master new-feature
```

 There are two types of local branches on your machine: non-tracking local branches, and tracking local branches.
#### 1.1.1 Non-tracking local branches 
  Non-tracking local branches are not associated with any other branch. To create one, run 
`$ git branch <branchname>`

####  1.1.2 Tracking local branches 
Tracking local branches are associated with another branch, usually a remote-tracking branch. To create one, run 
`$ git branch --track <branchname> [<start-point>]`

To view which one of your local branches are tracking branches, run
```
  $ git branch -vv
  master      b31f87c85 [origin/master] "my sample commit"
  new-feature b760e04ed "my branch is strong"
```
From this command's output, you can see that the local branch master is tracking the remote-tracking branch origin/master, and the local branch new-feature is not tracking anything.

"Tracking local branches" are useful. They allow you to run git pull and git push, without specifying which upstream branch to use. If the branch is not set up to track another branch, you'll get an error like this one:
```
  $ git checkout new-feature
  $ git pull
  There is no tracking information for the current branch.
  Please specify which branch you want to merge with.
  See git-pull(1) for details
  $ git pull <remote> <branch>
```
  If you wish to set tracking information for this branch you can do so with:

`$git branch --set-upstream new-feature <remote>/<branch>`

###  1.2. Remote-tracking branches (still on your machine)

  To view a list of all the remote-tracking branches on your machine, run
```
  $ git branch -r
  bitbucket/master
  origin/master
  origin/new-branch
```
  Each remote-tracking branch has a file under .git/refs/<remote>/:
```
$ tree -F .git/refs/remotes/
  .git/refs/remotes/
  ├── bitbucket/
  │   └── master
  └── origin/
  ├── master
  └── new-branch
```

  Think of your remote-tracking branches as your local cache for what the remote machines contain. You can update your remote-tracking branches using git fetch, which git pull uses behind the scenes.
  Even though all the data for a remote-tracking branch is stored locally on your machine (like a cache), it's still never called a local branch. (At least, I wouldn't call it that!) It's just called a remote-tracking branch.

##  Type of Branches (2) Branches on a remote machine:
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
    This git remote command queries the remote machine over the network about its branches. It does not update the remote-tracking branches on your local machine, use git fetch or git pull for that.
    From the output, you can see all the branches that exist on the remote machine by looking under the heading "Remote branches" (ignore lines marked as "stale").

    If you could log in to the remote machine and find the repository in the filesystem, you could have a look at all its branches under refs/heads/.

# Cheat sheet:
1. To delete a local branch, whether tracking or non-tracking, safely:
`git branch -d <brachname>`
2. To delete a local branch, whether tracking or non-tracking, forcefully:
`git branch -D <branchname>`
3. To delete a remote-tracking branch:
`git branch -rd <remote>/<branchname>`
4. To create a new local non-tracking branch:
`git branch <branchname> [<start-point>]`
5. To create a new local tracking branch: (Note that if <start-point> is specified and is a remote-tracking branch like origin/foobar, then the --track flag is automatically included)
`git branch --track <branchname> [<start-point]`
Example:
`git branch --track hello-kitty origin/hello-kitty
6. To delete a branch on a remote machine:
`git push --delete <remote> <branchname>`
7. To delete all remote-tracking branches that are stale, that is, where the corresponding branches on the remote machine no longer exist:
`git remote prune <remote>`
8. To check the status of the git repository. (which files are staged, added to the commit, etc.)
`git status`
9. To see the log of previous 'n' commits,
`git log -n`
10. To revert the changes just made in the file <filename>
`git checkout -- <filename>`
11. To see the difference between the local repository and the latest commit (HEAD)
`git diff [filename]`
12. THIS IS DANGEROUS!!: To remove the file from both working directory and git
`git rm`
13. To remove the file from git tracking, but still keep it in the working directory:
`git rm --cached`

    You may have noticed that in some commands, you use <remote>/<branch>, and other commands, <remote> <branch>.

    Examples: git branch origin/hello-kitty and git push --delete origin hello-kitty.
    It may seem arbritrary, but there's simple way to remember when to use a slash and when to use a space. When you're using a slash, you're referring to a remote-tracking branch on your own machine, whereas when you're using a  space, you're actually dealing with a branch on a remote machine over the network.


# Checkout

    The git checkout command lets you navigate between the branches created by git branch. Checking out a branch updates the files in the working directory to match the version stored in that branch, and it tells Git to record all new commits on that branch. Think of it as a way to select which line of development you’re working on.

To check out the specified branch, which should have already been created with git branch, run:
`git checkout <existing-branch>`
This makes <existing-branch> the current branch, and updates the working directory to match.

To create and check out <new-branch>, run
`git checkout -b <new-branch>`
    The -b option is a convenience flag that tells Git to run git branch <new-branch> before running git checkout <new-branch>. 


# HEAD in the Git

    HEAD points to the tip of the "current branch". When you switch branches with git checkout, the HEAD revision changes to point to the tip of the new branch.
    To see where the HEAD is pointing, run:
    cat .git/HEAD
    In my case, the output is:
```
$ cat .git/HEAD 
ref: refs/heads/master
```
It is possible for HEAD to refer to a specific revision that is not associated with a branch name. This situation is called a detached HEAD.


