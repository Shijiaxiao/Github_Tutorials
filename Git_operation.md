# Tutorial of Git

This is a tutorial of Git and its basic operations, which aims to help you get better understanding and use of Git.

## 1 What is Git?

Git is a distributed version control system (DVCS) that allows developers to track and manage changes to their codebase efficiently.

In Git, developers can work on a project collaboratively and keep a complete history of all changes made to the code. Git enables features like branching, merging, and distributed workflows, making it easier to manage code changes, collaborate with others, and maintain a history of a project's development.

> Key features of Git:
> * Distributed Version Control: Every developer has a full copy of the repository, which allows them to work offline and independently. Changes can be synchronized with remote repositories when needed.
> * Branching and Merging: Git makes it easy to create branches for new features or bug fixes and merge them back into the main codebase when they are ready.
> * Commit History: Git maintains a detailed history of all changes, making it possible to track who made each change, when it was made, and why.
> * Collaboration: Multiple developers can collaborate on the same project by pushing and pulling changes to and from a shared repository.
> * Security: Git uses cryptographic techniques to ensure the integrity and authenticity of code changes.


## 2 Local vs remote and Repository vs branch

A repository in Git is a container that holds the entire project's code and history, while a branch is a separate line of development within that repository, allowing developers to work on specific features or fixes independently before merging them into the main codebase.

In Git, the local repository resides on a developer's machine and contains the complete project history and code. The remote repository is hosted on a server (like GitHub or GitLab) and serves as a central hub where developers can share and collaborate on the code, enabling distributed development and remote synchronization.

> Tips of your repositoty:
* It is recommended that every repository include a **_README_**, **_LICENSE_**, and **_.gitignore_**.
* SSH of your remote repository: git@github.com:username/your_repository.git


### 2.1 What is **_"master"_**, **_"origin"_** and **_"origin/master"_**?

* **_"origin"_** is the usual name of remote repository.
* **_"master"_** is a one of the branches.
* **_"origin/master"_** is the **reference** of one of the branches of the remote repository. It represents the state of the "master" branch of the remote repository.

``` zsh
# Usually local repository does not have a name, if you want to name it, run the following command during initialization:
git init local_repository_name

# You can view the differences between local and remote branches with this command:
git diff master origin/master
```

### 2.2 What is **"reference"**

A Reference in Git is a **_ pointer_** or **_label_** that points to a specific commit, which make the Git repository's history and branch structure easy to manage and navigate.

> Types of reference:
* Branch reference:
    Each branch has an associated reference that **points to the latest commit** on which the branch is located.
* Remote branch reference:
    Remote branche reference **points to the latest commit** on a branch of the remote repository.
* Label references:
    Label reference **points to a specific commit such as a software release**, and it usually doesn't move.


## 3 Manage you code with Git

### 3.1 Initialize a Git repository and first commit
``` zsh
git init (your_repository_name)
git add .
git commit -m "first commit"
git branch -M master       # Rename local branch to "master"(mostly "main" at first).
git remote add origin git@github.com:username/your_repository.git
git push -u origin master  # "-u" at first, set remote brach to the upstream one.
```

**3.1.1 Difference between "-M" and "-m":**
* "-M" is force, it will cover duplication of name.
* "-m" is not force, it won't cover duplication of name.

**3.1.2 What is "-u" for?**
* It can set remote brach to the upstream one.
* You can use the following simple commands to operate git after set remote brach to the upstream one:
``` zsh
git fetch
git merge
git pull
git push
```

### 3.2 Clone an existing repository online
> You can clone the whole repository(the whole repository folder) with the following comand:
``` zsh
git clone git@github.com:Shijiaxiao/repository.git
```

### 3.3 Update local repository from remote repository

**3.3.1 Fetch and merge from GitHub**
``` zsh
git fetch origin master     # "git fetch" if remote brach has been setto the upstream one.
git checkout origin/master  # Checkout code of remote branch of repository
git checkout master         # Back to local branch
git merge origin/master     # Merge them after check. using "git merge" if remote brach has been setto the upstream one.
```

**3.3.2 Pull from GitHub(automatically merge)**
``` zsh
git pull origin master      # Use "git pull" if remote brach has been setto the upstream one.
```

**3.3.3 Add and commit change, save change to history**
``` zsh
git add .
git commit -m "edit comment"
```

**3.3.4 Upload final edition of local branch to remote repository on GitHub**
``` zsh
git push origin master      # Use "git push" if remote brach has been setto the upstream one.
```


## 4 Other useful Git operations

### 4.1 Global settings
``` zsh
git config --global user.name "username"            
git config --global user.email "your_email"   
```

### 4.2 Check status of local repositpry
``` zsh
git status  
```

### 4.3 Correlat3 local repository with a remote one
``` zsh
git remote rm origin                                                 # Delete the previous association.
git remote add origin git@github.com:Shijiaxiao/repository.git       # Set association.
git remote set-url origin git@github.com:Shijiaxiao/repository.git   # Change association.
```

### 4.4 Check branchs of local and remote repository
``` zsh
git branch               # Check all local branches.
git branch -r            # Check all remote branches.
git branch -a            # Check all branches.
git branch -M/-m (name)  # Rename branch.
```

### 4.5 What should be added in **_.gitignore_**
``` zsh
.DS_Store
```
> You also can run the following command:
``` zsh
git rm --cached .DS_Store
```
