# Git and Github

Let’s start with the basics. Git is a version control system that allows you to track changes to your files and collaborate with others. It is used to manage the history of your code and to merge changes from different branches. I can understand that as of now these terms like version control, branches, and merges are not familiar to you. But don’t worry, we will learn them in this tutorial.

## Check your git version

#### To check your git version, you can run the following command

```
git --version
```

## Repository

A repository is a collection of files and directories that are stored together. It is a way to store and manage your code. A repository is like a folder on your computer, but it is more than just a folder. It can contain other files, folders, and even other repositories. You can think of a repository as a container that holds all your code.

#### To see the current state of your repository

```
git status
```

## Your config settings

#### Let’s setup your email and username in this config file. I would recommend you to create an account on github and then use the email and username that you have created.

```
git config --global user.email "your-email@example.com"

git config --global user.name "Your Name"
```

#### Check your config settings

```
git config --list
```

## Creating a repository

#### Creating a repository is a process of creating a new folder on your system and initializing it as a git repository. It’s just regular folder to code your project, you are just asking git to track it. To create a repository, you can use the following command

```
git status

git init
```

## Stage

#### Stage is a way to tell git to track a particular file or folder. You can use the following command to stage a file

```
git init

git add <file> <file2>

git status
```

## Commit

#### Here we are committing the changes to the repository. We can see that the changes are now committed to the repository. The -m flag is used to add a message to the commit. This message is a short description of the changes that were made. You can use this message to remember what the changes were. Missing the -m flag will result in an action that opens your default settings editor, which is usually VIM. We will change this to vscode in the next section

```
git commit -m "commit message"

git status
```

## Logs

#### This command will show you the history of your repository

```
git log

git log --oneline
```

## Gitignore

#### Gitignore is a file that tells git which files and folders to ignore. It is a way to prevent git from tracking certain files or folders. You can create a gitignore file and add list of files and folders to ignore.

Example:

```
node_modules
.env
.vscode
```

# Branches in git

Branches are a way to work on different versions of a project at the same time. They allow you to create a separate line of development that can be worked on independently of the main branch. This can be useful when you want to make changes to a project without affecting the main branch or when you want to work on a new feature or bug fix.

## Creating a new branch

#### To create a new branch, you can use the following command

```
git branch

git branch bug-fix

git switch bug-fix

git switch master

git switch -c dark-mode

git checkout orange-mode
```

## Merging branches

### Fast forward merge

This one is easy as branch that you are trying to merge is usually ahead and there are no conflicts. When you are done working on a branch, you can merge it back into the main branch. This is done using the following command:

```
git checkout main

git merge bug-fix
```

### Not fast-forward merge

In this type of merge, the master branch also worked and have some commits that are not in the bug-fix branch. This is a not fast-forward merge. When you are done working on a branch, you can merge it back into the main branch. This is done using the following command

```
git checkout main

git merge bug-fix
```

## Rename a branch

#### You can rename a branch using the following command:

```
git branch -m <old-branch-name> <new-branch-name>
```

## Delete a branch

##### You can delete a branch using the following command:

```
git branch -d <branch-name>
```

## Checkout a branch

#### You can checkout a branch using the following command:

```
git checkout <branch-name>
```

## List all branches

#### You can list all branches using the following command:

```
git branch
```

# Rebase

Rebase is a powerful tool in Git that allows you to move a branch to a new starting point. It effectively replays the commits from the original base onto the new base. This can be useful for keeping a cleaner, linear project history.

Here’s a flow example of using git rebase with all the commands involved:

Suppose you have a feature branch called feature-branch that you want to rebase onto the main branch.

#### Ensure you are on the branch you want to rebase

```
git checkout feature-branch

git rebase main
```

# Adding code to remote repository

Now that you have setup your ssh key and added it to your github account, you can start pushing your code to the remote repository

#### Create a new Repo on your system first, add some code and commit it.

```
git init

git add <files>

git commit -m "commit message"
```

## Check remote url setting

#### You can check the remote url setting by running the following command:

```
git remote -v
```

## Add remote repository

#### You can add a remote repository by running the following command:

```
git remote add origin <remote-url>
```

#### Here `<remote-url>` is the url of the remote repository that you want to add and `origin` is the name of the remote repository. This origin is used to refer to the remote repository in the future.

```
git remote add origin https://github.com/hiteshchoudhary/chai-something.git
```

## Push code to remote repository

`git push remote-name branch-name`

Here remote-name is the name of the remote repository that you want to push to and branch-name is the name of the branch that you want to push.

```
git push origin main
```

## Setup an upstream remote

Setting up an upstream remote is useful when you want to keep your local repository up to date with the remote repository. It allows you to fetch and merge changes from the remote repository into your local repository.

To set up an upstream remote, you can use the following command:

```
git remote add upstream <remote-url>
```

or you can use shorthand:

```
git remote add -u <remote-url>
```

#### You can do this at the time of pushing your code to the remote repository.

```
git push -u origin main
```

## Get code from remote repository

There are two ways to get code from a remote repository:

#### 1. fetch the code

#### 2. pull the code

Fetch the code means that you are going to download the code from the remote repository to your local repository. Pull the code means that you are going to download the code from the remote repository and merge it with your local repository.

### Fetch code

To fetch code from a remote repository, you can use the following command:

```
git fetch <remote-name>
```

### Pull code

To pull code from a remote repository, you can use the following command:

```
# git pull <remote-name> <branch-name>

git pull origin main
```
