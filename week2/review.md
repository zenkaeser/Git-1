This is a review for HackYourFuture Git advanced. It has the following sections:

1. Github and remotes
2. Git branches
3. Pull requests
4. Forking Workflow


# 1. Github and remotes

This is just a quick review about pushing, pulling, and fetch. The complete review can be found [here](https://github.com/HackYourFuture-CPH/Git/blob/master/week1/review.md).

## 1.1 What is remote ?

Before anything else, let's just clarify what is a remote.
If you're using Git collaboratively, you'll probably need to sync your commits with other machines or locations. In Git terminology, each machine or location is called a remote, and each one may have one or more branches. Most often, you'll have just one remote, named `origin`, which is a git repository in your own github account. But if you are using the forking workflow you'll probably have a remote named `upstream` as well.

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


# 1.2 Adding a remote to your local repository

If you have not cloned an existing repository on github and want to connect your repository to a remote github repository, you need to add it with

```
$ git remote add origin https://github.com/marta_matos/my_first_repo.git
```

Replace the URL with the URL repository that you actually want to add.
Also, remember that `origin` is just a place holder, and the convention is to use `origin` for a repository that is in your own github account and `upstream` for a repository that is in someone else's github account (see the forking worklow).

Now you are able to push your changes to the selected remote server i.e. your remote repository on GitHub.


## 1.3 Pushing, pulling, fetching changes to/from Github

To send any changes in a given branch on your local repository to your remote repository, go to that branch (`<branch_name>`) and execute

```
$ git push origin <branch_name>
```

However, this command will fail if there are changes in the remote repository that you do not have on your local machine. In that case you first need to get the changes from the remote repository to your local machine. To do so you do:

```
$ git pull origin <branch_name>
```

As a best practice, you should always do this before you push any changes into the remote repository.

If instead of getting the new changes from the remote repository into your local machine you just want to know if there are any changes, you can do

```
$ git fetch origin <branch_name>
```

Then if you do `git diff origin/<branch_name>` it will tell you any differences between your local `<branch_name>` and `origin/<branch_name>` (i.e. the `<branch_name>` branch on your github repository).
If you then want to incorporate those changes with your local `<branch_name>` you do:

```
git merge origin/<branch_name>
```

Doing `git fetch` followed by `git merge` is equivalent to doing `git pull`.

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


# 2 Branches

## 2.1 Why Branches ?

To expand.
Trees need branches to expand.
Banks needs (office) branches to expand.
Company needs (code) branches to expand.
E.g. Branches for Bugs, testing, featuers, production, staging etc.


## 2.2 Types of Branches

On your local machine, you've got three types of branches:
 1. local branches : non-tracking
 2. local branches : tracking
 3. remote-tracking branches

On a remote machine, you have just one type of branch.

## Types of Branches (1) Branches on your machine:

### 2.2.1 Local branches

 To view a list of all the local branches on your machine, run
```
$ git branch
 master
 new-feature
```

There are two types of local branches on your machine: non-tracking local branches, and tracking local branches.


#### 2.2.1.1 Non-tracking local branches

  Non-tracking local branches are not associated with any other branch in the remote repository. To create one, run

```
$ git branch <branch_name>
```


####  2.2.1.2 Tracking local branches

Tracking local branches are associated with another branch on the remote repository, usually a remote-tracking branch. To convert an existing non-tracking local branch into a tracking local branch do:

```
$ git branch -u <remote>/<branch_name>
```

Where <remote> will typically be `origin` or `upstream`.

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


###  2.2.2 Remote-tracking branches (still on your machine)

To view a list of all the remote-tracking branches on your machine, run

```
  $ git branch -a
  bitbucket/master
  origin/master
  origin/new-branch
```

Think of your remote-tracking branches as your local cache for what the remote machines contain. You can update your remote-tracking branches using `git fetch <remote> <branch_name>`, which `git pull` uses behind the scenes.
Even though all the data for a remote-tracking branch is stored locally on your machine (like a cache), it's still never called a local branch. (At least, I wouldn't call it that!). It's just called a remote-tracking branch.


##  2.3.3 Branches on a remote machine

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



# 3. Pull requests

Pull requests make it easier for developers to collaborate. They provide a user-friendly (web) interface for discussing proposed changes before integrating them into the official project.
In the simplest form, pull requests are a means for a developer to notify a team member that they have completed a feature. But the pull-request is more than just a notification. It's a dedicated forum where teammates can post feedback, push follow-up commits.
Even though it is named a pull request it is more like a merge request, where you ask for permission to merge a branch into another branch.

## What does a pull request contain:
When you create a pull request, you want another developer to pull a branch from your repository into their repository. This means that you need to provide 4 pieces of information to create a pull request:
* the source repository
* the source branch
* the destination repository
* the destination branch

Pull requests can be used in conjunction with various workflows:
* Feature-branch workflow
* Gitflow workflow
* Forking workflow



# 4. Forking Workflow
In the Forking workflow, a developer pushes a completed feature to their own public repository instead of a shared one.
After that, they create a pull request to let the project maintainer know that it's ready for review.

Since each developer has their own public repository, the pull request's source repository will differ from its destination repository.
The source repository is the developer's public repository and the source branch is the one that contains the proposed changes.
If the developer is trying to merge the feature into the main codebase, then the destination repository is the official project and  the destination branch is "master".

Steps in Forking Workflow:
* You fork a public repository (`upstream`)
* You clone the repository (so that you have a working copy on your machine)
* You create a (feature) branch and make some commits
* You push the branch in your repository (`origin`)
* You create a pull request by navigating to your forked repository

But before you push the branch to your repository, remember to update your (feature) branch with the latest changes on the branch `master` in the `upstream` repository.


