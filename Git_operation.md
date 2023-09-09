# A Tutorial to Github Repository
It is recommended that every repository include a **_README_**, **_LICENSE_**, and **_.gitignore_**.

My repository SSH: git@github.com:Shijiaxiao/repository.git



## Initialize and first commit
``` zsh
git init
git add .
git commit -m "first commit"
git branch -M master (first commit)
git remote add origin git@github.com:Shijiaxiao/repository.git
git push (-u) origin master
```


## Clone an existing repository online
Clone the whole repository(1 folder)
``` zsh
git clone git@github.com:Shijiaxiao/repository.git
```


## Update

### Fetch and merge from github
``` zsh
git fetch origin master
git checkout origin/master  # 查看远程分支部分代码
git checkout master         # 回到本地分支
git merge origin/master     # 检查无误后合并
```

### Pull from github(automatically merge)
``` zsh
git pull origin master
```

### Commit change
``` zsh
git add .
git commit -m "edit comment"
```

### Upload to github
``` zsh
git push origin master
```


## Useful operations

### Global settings
``` zsh
git config --global user.name "ShiJiaxiao"        # Git全局设置
git config --global user.email "jxshi2003@sina.com"   # Git全局设置
```

### Status check
``` zsh
git status      # 查看本地仓库状态
git branch      # 查看本地所有分支
git branch -r   # 查看远程所有分支
git branch -a   # 查看所有分支
```

### Correlation between local and remote repository
``` zsh
git remote rm origin                                                   # 删除之前的关联
git remote add origin git@github.com:Shijiaxiao/repository.git       # 设置关联
git remote set-url origin git@github.com:Shijiaxiao/repository.git   # 更改关联关联
```

### Branch of local and remote repository
``` zsh
git branch       # 查看本地所有分支
git branch -r    # 查看远程所有分支
git branch -a    # 查看所有分支
```

### What should be added in **_.gitignore_**
``` zsh
.DS_Store
git rm --cached .DS_Store
```