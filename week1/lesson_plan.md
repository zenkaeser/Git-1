# Lesson plan

 1. Install git/git bash

 2. Configure git
   - `git config --global user.name "name"`
   - `git config --global user.email "email"`
   - `git config --global core.editor "code -w"` (without `-w` the commit is aborted with empty message)

 3. What is Git
   - git is version control software, widely used by software developers (and not only)

 4. What is version control
   - show example with google docs
   - git does the same but for all files in a given folder/repository
   - show repository for vscode as an example of a software built using Git to manage all the code
   - also git allows you to have branches and work on multiple tasks at the same time, a bit like copying folders

 5. Command line basics
   - `pwd`, and explain how paths work
   - `ls`
   - `cd`
   - `mkdir`
   - do a little exercise

 6. Git vs. github
   - slide 2

 7. What is a repository and how to create one
   - kind of a folder, but not all files in the folder have to be in the repository
   - slide 3

 8. The commit
   - slide 4

 9. How to save/commit changes in your repository
   - slide 5

 10. What is a commit (technical side)
   - slide 6

 11. Explain/show what happens after each git add and git commit
   - slides 7-16
   - also show a lot of git status and git log

 12. Do a little exercise where the students have to create their repo, add files, and commit the changes

 13. Go into Github
   - create github repo
   - add remote
   - push current changes
   - show how to do first, have students do it on their own after

 14. Address a conflict
   - do a change on github
   - change the same line locally
   - push to github (get error)
   - pull from github (get conflict)
   - solve conflict
   - push to github
   - do at the same time with the students

 15. Branches  [if time allows]
   - stick local branches
   - do little exercise

 16. How to go back in history [if time allows]
   - git checkout
   - git revert
   - git reset -> do not use please :)
   - https://www.atlassian.com/git/tutorials/undoing-changes
   - https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting

