# Lesson plan

 1. What is Git
    - git is a version control software, widely used by software developers (and not only)

 2. What is version control
    - show example with google docs
    - git does the same but for all files in a given folder/repository
    - show repository for vscode as an example of a software built using Git to manage all the code
    - also git allows you to have branches and work on multiple tasks at the same time, a bit like copying folders

 3. Install git/git bash

 4. Configure git
    - `git config --global user.name "name"`
    - `git config --global user.email "email"`
    - `git config --global core.editor "code -w"` (without `-w` the commit is aborted with empty message)

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

 12. Explain/show what happens after git push
     - slide 17
     
 13. Do a little exercise where the students:
     - create a folder named `class_playground` under `hyf-homework/Git/week1`
     - add some files
     - commit the changes
     - push current changes

 14. Branches
     - go trough the homework workflow [have slides showing each step]:
         a) create a branch
         b) do commits
         c) push to github
         d) create pull request
         e) merge with master
         f) update local master
      - do an exercise where the students do parts a) to d)