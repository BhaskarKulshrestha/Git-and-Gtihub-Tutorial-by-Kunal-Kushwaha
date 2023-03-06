

# GIT AND GITHUB TUTORIAL

Git is the free and open source distributed version control system that's responsible for everything GitHub
related that happens locally on your computer. This cheat sheet features the most important and commonly
used Git commands for easy reference.



## git init
    git init is one way to start a new project with Git
    This folder where a is thell the history of the file is saved.

## ls -a : 
    show all the hidden- [GIT AND GITHUB TUTORIAL](#git-and-github-tutorial)

## cat file_name
    shows all the content of the file that is contained in the given file.

## git status
    The git status command displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.

    basically it will show that the file is tracked or untracked

## git add individual_file_name  
    individully selects a files that is to be to be saved.

## git add .
    selects all the files that is to be saved.

<strong>What actually git add do ?</strong>
    
    The git add command adds a change in the working directory to the staging area. It tells Git that you want to include updates to a particular file in the next commit.

## git commit -m "<commit_message>"
     git commit -m '<commit_message>' at the command line to commit new files/changes to the local repository

<h4>To write something on comand line use:</h4>
    vi file_name

### To exit from the VI editor use:

    If you want to save your changes and quit, press Esc then type :wq and hit Enter or ↵ or on Macs, Return .

### cat.file_name
    Display all the content that is basically present in the file.

### git restore --staged Filename

    The "restore" command helps to unstage or even discard uncommitted local changes.

    On the one hand, the command can be used to undo the effects of git add and unstage changes you have previously added to the Staging Area.

    On the other hand, the restore command can also be used to discard local changes in a file, thereby restoring its last committed state.

## git log

    Git log is a utility tool to review and read a history of everything that happens to a repository.

## git reset

    The git reset command is a complex and versatile tool for undoing changes. It has three primary forms of invocation. These forms correspond to command line arguments --soft, --mixed, --hard.
     The three arguments each correspond to Git's three internal state management mechanism's, The Commit Tree (HEAD), The Staging Index, and The Working Directory.

When to use reset in git?

reset is the command we use when we want to move the repository back to a previous commit .

----------------------------------

## What is meant by stash?
    Stash means to store (changes) safely in a hidden place (the stash stack). Stashing the current working directory's staged or unstaged changes or untracked files and then storing them in the stash stack reverts the current working directory to the last commit.

![](https://static.javatpoint.com/tutorial/git/images/git-stash.png)
## git stash
    The git stash command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy. 
------------
**NOTE: we can work on git stash sfter we have done git add . only,else it will note work.**

------------
#### <i>How to reverse back the action of git Stash? </i>

## git stash pop 
    git stash pop is a Git command that applies the changes stored in the most recent stash to your current working directory and then removes that stash from your stash list.


----------------------------------
    Git stash is a command that allows you to temporarily save changes that you've made to your working directory without committing them to your Git repository. This can be useful if you're in the middle of working on a particular branch but need to switch to another branch to work on something else.
-----------------------------
    The git stash command works by taking all the changes you've made to your working directory and storing them in a special Git object called a stash. The stash object includes both the changes you've made to tracked files as well as any new files you've added to your working directory.

*example*
Here's an example of how to use git stash:

Make some changes to your working directory.

    $ echo "New line of code" >> myfile.txt

$ echo "New line of code" >> myfile.txt

    $ git status
    On branch master
    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified:   myfile.txt

    no changes added to commit (use "git add" and/or "git commit -a")

Stash your changes.

    $ git stash
    Saved working directory and index state WIP on master: 3c8e8d3 Added new feature

Check the status of your working directory again.

    $ git status
    On branch master
    nothing to commit, working tree clean

Switch to a different branch.

    $ git checkout other-branch
    Switched to branch 'other-branch'

Pop the stash to apply your changes to the new branch.

```
$ git stash pop
On branch other-branch
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified:   myfile.txt

no changes added to commit (use "git add" and/or "git commit -a")
    Dropped refs/stash@{0} (a10b46c8c996d7397d1f6026e791e6b1d6f92ec6)
```

In this example, we first made some changes to a file called myfile.txt. We then used the git stash command to save those changes to a stash object. We then switched to a different branch and used the git stash pop command to apply the changes from the stash object to our new branch. After running git stash pop, the changes we made to myfile.txt were successfully applied to our working directory on the other-branch branch.

## git stash clear
    git stash clear is a Git command used to remove all saved stashes from the stash list.

    If we did it all the unsaved work will be permanently deleted.


## git remote
    The git remote command lets you create, view, and delete connections to other repositories
## git remote -v
    is a Git command that is used to display a list of remote repositories that are currently associated with your local Git repository, along with their corresponding URLs.

## git remote add origin "path name"
    to connect the repo of the gitub with the git or our local system.

    remote means that we are basically working with the URL's.

    add means we are adding a url

    origin means what is the name of the url that is going to be add.

    path name : is the url of your created repo.    

## create a new repository on the command line
    echo "# temp1" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/BhaskarKulshrestha/temp1.git
    git push -u origin main

    echo "# temp1" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/BhaskarKulshrestha/temp1.git
    git push -u origin main

## git push origin branch_name
    it basically pushed the commmited file to the  required branch.

## What is branch ?
    In Git, branches are a part of your everyday development process. Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes.

    Branching offers a way to work on a new feature without affecting the main codebase

![](https://wac-cdn.atlassian.com/dam/jcr:389059a7-214c-46a3-bc52-7781b4730301/hero.svg?cdnVersion=812)


## What is head ?
    
    When working with Git, only one branch can be checked out at a time - and this is what's called the "HEAD" branch. Often, this is also referred to as the "active" or "current" branch. Git makes note of this current branch in a file located inside the Git repository, in . git/HEAD .

![](https://static.javatpoint.com/tutorial/git/images/git-head.png)


## <strong>git branch branch_name</strong>
    The git branch command lets you create, list, rename, and delete branches. It doesn't let you switch between branches or put a forked history back together again. For this reason, git branch is tightly integrated with the git checkout and git merge commands.

## <strong>git checkout branch_name</strong>
    The git checkout command lets you navigate between the branches created by git branch .

the branches form a directed acyclic graph

## git merge  name_of_the_current_branch 
    Merging is Git's way of putting a forked history back together again. The git merge command lets you take the independent lines of development created by git branch and integrate them into a single branch.

---------------------------------------------------
<i>To solve the problem :</i>

error: Merging is not possible because you have unmerged files.

hint: Fix them up in the work tree, and then use 'git add/rm < file >'

hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

### use : git pull origin main
--------------------------------------

## fork in github
    A fork is a new repository that shares code and visibility settings with the original “upstream” repository.

## cloning in github
    When you clone a repository, you copy the repository from GitHub.com to your local machine.

## what is upstream URL / upstream repository in github.
    Upstream generally refers to the original repo that you have forked

## what is origin URL / origin repository
    It is basically the repository in your own account

## what git remote add upstream https://github.com/Global-Code-Hunters/College-WEBD.git signifies

    This command is used to add a new remote repository named "upstream" to a local Git repository.

    The URL "https://github.com/Global-Code-Hunters/College-WEBD.git" specifies the location of the remote repository.

    Once added, the local repository can pull changes from the upstream repository using the git pull upstream command and push changes to the upstream repository using the git push upstream command.

    The "upstream" name is a convention used to refer to the original repository that a forked repository was created from, and is commonly used when working on collaborative projects on GitHub.


------------------------------------------------------------

### NOTE : *it is advised to make a new branch every time whenever you have to add a new feature , because one branch can open only one pull request.*

-------------------------------

## Removing a commit from the pull request and force pushing to it

1. First use the reset method to revert back to the previous desired location using
```
git reset hashid
```

2. move the unstagged file into the stash using 
```
    git stash
```

3. Now push the changed file using -f keyword

```
    git push origin BRANCH_NAME -f
```
**here we have to use force push because the online repository contains the commit that our repositor does not conain , as we have deleted that commit from our system so we have to force push them || here -f denotes the force pushing ||**


## git fetch --all --prune
    featches from all the branches along with who are deleted

## what is git fetch ?
    git fetch is a primary command used to download contents from a remote repository
## git fetch --all
    A power move which fetches all registered remotes and their branches

    This command is a Git command that updates your local repository with changes from all remote branches, and prunes any remote-tracking branches that are no longer on the remote repository.
-------------------------------------------

    Here's what each part of the command means:

    git fetch: This Git command is used to retrieve changes from a remote repository and store them in your local repository. It does not modify your local branch or working directory.

    --all: This flag tells Git to fetch changes from all remote branches, not just the default remote branch (usually "origin").

    --prune: This flag tells Git to remove any remote-tracking branches that no longer exist on the remote repository. Remote-tracking branches are references to the state of remote branches, and can become stale if the corresponding branch on the remote repository is deleted or renamed.

    So, the command git fetch --all --prune will retrieve all changes from all remote branches and update your local repository, and remove any stale remote-tracking branches that no longer exist on the remote repository. This is a useful command to run periodically to ensure that your local repository is up-to-date with the latest changes on the remote repository, and to clean up any outdated references.


##  git reset --hard upstream/master

    This command is a Git command that resets your local repository's current branch to match the upstream/master branch of the remote repository.

    Here's what each part of the command means:

    git reset: This Git command is used to move the current branch pointer to a specific commit, and optionally modify the working directory and/or staging area.

    --hard: This flag tells Git to reset both the branch pointer and the working directory to match the specified commit. Any changes you have made in your working directory that have not been committed will be lost.

    upstream/master: This is the name of the remote branch you want to reset your local branch to match. In Git, "upstream" is a shorthand name for the remote repository that your local repository is synchronized with, and "master" is the name of the branch in that remote repository that you want to use as the reference for the reset.
    
    So, the command git reset --hard upstream/master will completely discard any changes in your working directory and staging area, and reset your current branch to match the upstream/master branch in the remote repository. It's a destructive operation, so use it with caution.


## git pull upstream master

    This command is a Git command that pulls changes from the upstream/master branch of the remote repository and integrates them into the current branch of your local repository.

    Here's what each part of the command means:

    git pull: This Git command is used to fetch changes from a remote repository and integrate them into the current branch of your local repository. It combines the git fetch and git merge commands in a single step.

    upstream: This is the name of the remote repository that your local repository is synchronized with. It is usually a shorthand name for the URL of the remote repository.

    master: This is the name of the branch in the remote repository that you want to integrate changes from. In this case, you want to integrate changes from the upstream/master branch.

    So, the command git pull upstream master will fetch any new changes from the upstream/master branch of the remote repository and merge them into the current branch of your local repository. If there are any conflicts between your local changes and the remote changes, Git will prompt you to resolve the conflicts before completing the merge. This command is useful for keeping your local repository up-to-date with the latest changes in the remote repository. 