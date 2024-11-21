# Part 1: Introduction to Version Control and Git

## Task 1: Install and Configure Git
1.Configure Git with your username and email:

    git config --global user.name "Your Name"
    git config --global user.email "your-email@example.com"
* Answer :- git config --global command is use for set and manage configuration settings, like user name, email.


2.View your Git configuration:

    git config --list
* Answer:- --list command is use for get details of configuration settings which are active.


## Task 2: Initialize a Repository
1.Create a new project folder and navigate to it:

    1)mkdir MyProject
* Answer:- Make New folder


        2)cd MyProject
* Answer:- Go to Folder.

2.Initialize it as a Git repository:

    git init
* Answer:- Repo ko initialize karne ke liye.

## Task 3: Create a File and Make Multiple Commits
1.Create a new file and add content:
  
    echo "My First Project" > README.md
* Answer:- echo use for create a new file with message.

2.Stage the file:

    git add README.md
* Answer:- add file to staging area.

3.Commit the file:

    git commit -m "Initial commit: Added README.md"
* Answer:- commit file for push.

4.Make changes to the file:

    echo "Added a description" >> README.md
* Answer:- change the file

5.Stage and commit the changes:

    git add README.md
* Answer:- add second commited file to stating area.

         git commit -m "Updated README with a description"
* Answer:- updated file for commit.

## Task 4: Check Status and Log
1.Check the repository’s current status:

    git status
* Answer:- this command shows the current state of the working directory and staging area. also tells that which files are modifieded,untracked,stage for commit.

2.View commit history in detail:

    git log --oneline --graph --decorate
* Answer:- for view commit history.

## Task 5: Create and Clone a Repository
1. Create a repository on GitHub named `example-repo`.

* Answer:- Make new repo. 
2. Clone it locally:  

        git clone http://codinggita.com/example-repo
* Answer:- make copy of other repo.

## Task 6: Understanding the Git Workflow
1. Make changes to a file in the working directory: 

       echo "Workflow example" > workflow.md

* Answer:- Making Changes in file

2. Stage the file:  

       git add workflow.md
* Answer:-add file to staging area.

3. Commit the file to the repository:  

        git commit -m "Added workflow example"
* Answer:- commit the file.
---
# Part 2: Working with Repositories
## Task 7:Branching and Merging
1.Create a new branch for a feature:

    git branch feature-login
* Answer:- create a new branch named login.

        git checkout feature-login
* Answer:- switch to new branch.

2.Add a new file and commit changes:
  
    echo "Login Page" > login.html
    git add login.html
    git commit -m "Added login page"
* Answer:- add new file with massage ,add to staging area and commit

3.Merge the feature branch into main:

    git checkout main
    git merge feature-login
* Answer:- change the branch and merge both branch.

## Task 8: Handling Merge Conflicts
1.Create two branches:

    git branch branch-A
    git branch branch-B
* Answer:- create 2 new branches.

2.Modify the same line in README.md in both branches.

3.Merge branch-A into main:

    git checkout main
    git merge branch-A
* Answer:- switch branch and merge them

4.Attempt to merge branch-B into main (this will cause a conflict):
    
    git merge branch-B

5.Resolve the conflict manually in README.md, then:
  
    git add README.md
    git commit -m "Resolved merge conflict between branch-A and branch-B"

## Task 9: Renaming and Deleting Branches
1.Rename a branch:

    git branch -m old-branch-name new-branch-name
* Answer:- changing name of branch

2.Delete a branch:

    git branch -d feature-login
* Answer:- delete branch.
---
# Part 3: Advanced Git Operations
## Task 10: Using Git Stash
1.Make changes to a file but don’t commit:

    echo "Temporary work" >> temp.md
* Answer:- changes in file.

2.Stash the changes:

    git stash
* Answer:- it saves uncommitted changes,which means It allows you to switch branches or work on something else.

3.View stashed changes:
    
    git stash list
* Answer:- it shows all the stashed changes which are saved in repository.

4.Apply the stashed changes:

    git stash apply
* Answer:- it's restores the recent stashed changes to your working directory without removing them from the stash list.

5.Drop the stash after applying:

    git stash drop
* Answer:-it's removes stash from the stash list.like its delete stash from list.

## Task 11: Rewriting History with Interactive Rebase
1.Create multiple commits:

    echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
    echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
    echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
* Answer:- create 3 new files with message , add to staging area and commit it.

2.Squash commits into one:
    
    git rebase -i HEAD~3
* Answer:-

-i :- it means that it allows you to modify,reorder ,give full control over how the commit history looks.

HEAD~3 :-This specifies The interactive rebase will only apply to last 3 commits.

## Task 12: Cherry-Picking Commits
1.Create a new branch:

    git checkout -b cherry-pick-example
* Answer:- create and switch to new branch.

2.Cherry-pick a specific commit from another branch:

    git cherry-pick <commit-hash>
* Answer:- This command takes a specific commit from another branch and applies it to current branch.in short it means that its copy text from another branch without merging it.

## Task 13: Tagging Commits
1.Tag the current commit:

    git tag -a v1.0 -m "Version 1.0 release"
* Answer:- creates an annotated tag named v1.0 with a message "Version 1.0 release.

2.Push the tag to the remote repository:

    git push origin v1.0
* Answer:- push the tag v1.0.

## Task 14: Working with Remote Repositories
1.Add a remote repository:

    git remote add origin <repository-url>
* Answer:-add remote repo.

2.Push your changes to the remote repository:

    git push origin main
* Answer:- push the changes.

## Task 15: Forking and Contributing
1.Fork a repository on GitHub.

2.Clone the fork locally:
    
    git clone <forked-repo-url>
* Answer:- copy of repo.

3.Create a new branch, make changes, and push:

    git checkout -b fix-typo
    echo "Typo fixed" >> README.md
    git add README.md
    git commit -m "Fixed a typo"
    git push origin fix-typo

4.Open a pull request on GitHub.

# Part 4: Additional Practice
## Task 16: Simulate Team Collaboration
1.Create a repository and share it with a friend.

2.Both make changes to the same file simultaneously.

3.Practice resolving merge conflicts and pushing changes.

* Answer:-

Two option

1>Do it with fork and pull request.

2>collabrate it repo to friend and make changes.

## Task 17: Git Ignore
1.Create a .gitignore file:

    echo "node_modules/" > .gitignore
* Answer:-create new file

2.Add files and ensure ignored files are not staged:

    git add .
* Answer:-add file to staging area.