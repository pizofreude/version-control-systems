# **Git 101: Version Control Systems for Dummies.**

A long time ago in a galaxy far, far away... there exist three types of Version Control Systems as data organizer:

1. Local Version Control System
2. Centralized Version Control System
3. Distributed Version Control System - Yes, Git!

These are the systems people actually used to organized their Product Lifecycle Management (PLM), i.e. source code, projects, files, simulation data so on and so forth.

The intention behind this page creation is to summarize the key notes for all VCSs & git related topics.


## **Contributing**

Contributions are wholeheatedly welcome. Feel free to open a pull request with changes.

## **1. Local Version Control System**

Let

FileName_v0.0.1.fileExtension

FileName_v0.0.2.fileExtension

:

:

FileName_v0.0.`N`.fileExtension

where `N = 1, 2, 3, ..., ∞`.

No code solution for data organizer.

## **2. Centralized Version Control System**

In short, centralized VCS is simply local VCS stored in cloud storage with collaboration capabilities.

User set their own file nomenclature and do collaboration work which the cloud storage hosting do smart backup automatically for the version control.

E.g.: MS Office Packages edited in OneDrive by multiple users simultaneously.

Yet another #NoCode solution for data organizer.

## **3. Distributed Version Control System**

Git is the software. It is the underlying technology behind the scene.

Git is the hero.

GitHub, GitLab, BitBucket, SourceForge and many others are cloud repositories and developer platform. These are examples of service that utilizing git software.

### **Essentials Commands for command-line interface (CLI)**

A deeper visualization of what happens under the hood of `git command`

### COMMIT ONLY SPECIFIC FILES:
`git add name-of-file && git commit -m 'commiting individual files'`

### CHANGING HISTORY
#### changing the last commit:
`git commit --ammend` that is if in your previous commit there's a file you forgot to commit and it was supposed to be part of the previous commit.

you add the file then you git ammend

For git amend never amend commits that have been pushed to remote repositories.

#### changing multiple commits:

`rebase -i` - is a command which allows us to interactively stop after each commit we’re trying to modify, and then make whatever changes we wish. We do have to tell this command which is the last commit we want to edit. For example, git rebase -i HEAD~2 allows us to edit the last two commits.

For git rebase never rebase a repository that others may work off of.

#### squashing commits
#### splitting commits

### WORKING WITH REMOTES
#### git push --force
this command is used when the remote repository contains files that your local environment doesn't, it overides the remote repo and destroys the files that are not present in your local directory but present in the remote repository.

git push --force is a very dangerous command, and it should be used with caution when collaborating with others.

#### git revert!
this undos the latest commit we just made.

###### N/B HEAD stands for the current commit

#### git push --force-with-lease
it’s a fail-safe! It checks if the branch you’re attempting to push to has been updated and sends you an error if it has.

For git push --force only use it when appropriate, use it with caution, and preferably default to using git push --force-with-lease.

#### Git reset
For git reset never reset commits that have been pushed to remote repositories.


`git rebase -i HEAD~2` - HEAD means our current commit, 2 means we can edit the last two commits.

### USING BRANCHES
to make new branches `git branch <branch name>`
to checkout to a branch `git checkout <branch name>`
to make a new branch and switch into it `git checkout -b <branch name>`
to see all the current branches you have `git branch`

git merge - pull whatever you were doing in other branches into the main/the branch you are currently are branch - `git merge <branch name>`
deleting a branch? `git branch -d <branch name>` if the branch has already been merged with main else use flag `-D`.

setting the default branch for all your repos `git config --global init.defaultBranch main`

when you create a new branch you need to push it to your github remote repo `git push origin <name of the repo>`

### git log

gives you a history of your previous commit

### git checkout -f

returns to the previously commited stage if you had made some changes but you hadn't committed them then.