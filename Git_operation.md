# A Tutorial to Github Repository
It is recommended that every repository include a **_README_**, **_LICENSE_**, and **_.gitignore_**.

My repository SSH: git@github.com:Shijiaxiao/repository.git



## 1. 仓库和分支，What is **_master_**, **_origin_** and **_origin/mmater_**

* **origin是远程仓库，master是分支**
* 通常本地仓库没有名字，如果想命名，初始化时运行以下语句：
``` zsh
git init local_repository_name
```

### master
"master"是你的本地主分支，通常是你当前工作的分支。本地主分支通常用于跟踪远程仓库的主分支（通常也是"master"分支），你可以在本地进行开发工作，然后将更改推送到远程仓库的"master"分支。

### origin
"origin"是Git中一个常见的远程仓库的默认别名（也可以自定义），通常用于指代你与之交互的远程仓库。

### origin/master
"origin/master"是远程仓库"origin"的"master"分支的引用。它表示远程仓库的"master"分支的状态。当你运行"git fetch origin"时，Git 会从远程仓库拉取最新的更改，包括更新"origin/master"引用的信息。

### 查看本地分支和远程分支的不同
``` zsh
git diff master origin/master
```


## 2. What is ##_Reference_**
Git中的引用（Reference是一种**_指针_**或**_标签_**，它指向一个特定的提交（commit）。引用通常用于标识和跟踪各种Git对象，最常见的引用类型是分支和标签。引用允许你轻松地查找和访问 Git 仓库中的不同提交。

引用使得Git仓库的历史记录和分支结构易于管理和浏览。你可以使用Git命令来查看和操作引用，如"git branch", "git checkout"等。

### 分支引用
分支是Git中的一个重要概念，每个分支都有一个关联的引用，它指向分支所在的最新提交。例如，"master"分支是一个引用，它**指向"master分支上的最新提交**。分支引用允许你轻松地切换和管理不同的分支。

### 远程分支引用
远程分支是与远程仓库相关联的分支，它们的引用通常具有形式如"origin/master"的名称。这些引用**指向远程仓库的分支上的最新提交**，允许你跟踪和拉取远程仓库的更改。

### 标签引用
标签是一种具有描述性名称的引用，通常用于标识特定的提交，如软件版本发布。标签引用指向一个特定的提交，它通常不会移动。



## 3. Initialize and first commit
``` zsh
git init
git add .
git commit -m "first commit"
git branch -M master       # Rename local branch to "master"(mostly main at first).
git remote add origin git@github.com:Shijiaxiao/repository.git
git push -u origin master  # "-u" at first, set remote brach to the upstream one.                     
```

### Difference between "-M" and "-m"
* -M is force, it will cover duplication of name.
* -m is not force, it won't cover duplication of name.

### What is "-u" for
* It can set remote brach to the upstream one.
After using "-u", you can use more simple commands to operate git. 
``` zsh
git fetch
git merge
git pull
git push
```


## 4. Clone an existing repository online
Clone the whole repository(1 folder)
``` zsh
git clone git@github.com:Shijiaxiao/repository.git
```


## 5. Update repository

### Fetch and merge from github
``` zsh
git fetch origin master     # "git fetch" if "-u" has been applied.
git checkout origin/master  # 查看远程分支部分代码
git checkout master         # 回到本地分支
git merge origin/master     # 检查无误后合并 "git merge" if "-u" has been applied.
```

### Pull from github(automatically merge)
``` zsh
git pull origin master      # "git pull" if "-u" has been applied.
```

### Commit change
``` zsh
git add .
git commit -m "edit comment"
```

### Upload to github
``` zsh
git push origin master      # "git push" if "-u" has been applied.
```


## 6. Useful operations

### Global settings
``` zsh
git config --global user.name "ShiJiaxiao"        # Git全局设置
git config --global user.email "jxshi2003@sina.com"   # Git全局设置
```

### Status check
``` zsh
git status            # 查看本地仓库状态
```

### Correlation between local and remote repository
``` zsh
git remote rm origin                                                 # 删除之前的关联
git remote add origin git@github.com:Shijiaxiao/repository.git       # 设置关联
git remote set-url origin git@github.com:Shijiaxiao/repository.git   # 更改关联关联
```

### Branch of local and remote repository
``` zsh
git branch            # 查看本地所有分支
git branch -r         # 查看远程所有分支
git branch -a         # 查看所有分支
git branch -M/-m ...  # Rename branch.
```

### What should be added in **_.gitignore_**
``` zsh
.DS_Store
git rm --cached .DS_Store
```