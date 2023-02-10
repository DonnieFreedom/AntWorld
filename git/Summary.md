# git

### git 基本概念

- 工作区、暂存区和版本库
  - **工作区(Workspace)：**就是你在电脑里能看到的目录。
  - **暂存区(stage/index)：**一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
  - **版本库(Repository)：**工作区有一个隐藏目录 **.git**，这个不算工作区，而是 Git 的版本库。
  - **远程仓库(Remote)** :托管代码的平台（GitHub ，码云)
  - [runoob图片](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)
    - 图中左侧为工作区，右侧为版本库。在版本库中标记为 "index" 的区域是暂存区（stage/index），标记为 "master" 的是 master 分支所代表的目录树。
    - 图中我们可以看出此时 "HEAD" 实际是指向 master 分支的一个"游标"。所以图示的命令中出现 HEAD 的地方可以用 master 来替换。
    - 图中的 objects 标识的区域为 Git 的对象库，实际位于 ".git/objects" 目录下，里面包含了创建的各种对象及内容。
    - 当对工作区修改（或新增）的文件执行 **git add** 命令时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的ID被记录在暂存区的文件索引中。
    - 当执行提交操作（git commit）时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。
    - 当执行 **git reset HEAD** 命令时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。
    - 当执行 **git rm --cached <file>** 命令时，会直接从暂存区删除文件，工作区则不做出改变。
    - 当执行 **git checkout .** 或者 **git checkout -- <file>** 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区中的改动。
    - 当执行 **git checkout HEAD .** 或者 **git checkout HEAD <file>** 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。

### 常规使用

- [git官方文档](https://git-scm.com/doc)

- 创建本地仓库并关联远程仓库地址, 使之成为master仓库

  ```
  echo "# h1" >> README.md
  git init
  git add README.md
  git commit -m 'init'
  git branch -M 分支名master # 重命名分支名
  git remote add origin 远程仓库地址 # 关联远程仓库地址 
  git push -u origin 分支名master # 推送一个分支到远程仓库
  ```

- 将本地仓库推送到远程仓库地址, 使之成为master仓库

  ```
  git remote add origin https://github.com/DonnieFreedom/Empty.git
  git branch -M master
  # git pull -–rebase origin master # 把远程库中的更新合并到（pull=fetch+merge）本地库中，–-rebase的作用是取消掉本地库中刚刚的commit，并把他们接到更新后的版本库之中
  git push -u origin master
  ```

  

- 即新建远程分支:本地创建仓库时, 推送到远程分支, 而远程库与本地库不一致时需要git pull

  - ```
    git init 
    git remote add origin https://github.com/DonnieFreedom/Empty.git
    git branch -M 新建分支名
    # git pull -–rebase origin master # 把远程库中的更新合并到（pull=fetch+merge）本地库中，–-rebase的作用是取消掉本地库中刚刚的commit，并把他们接到更新后的版本库之中
    git push -u origin 新建分支名
    ```
  
  

- 拉取指定分支到本地分支

  - ```
    git checkout -b 本地分支名 origin/远程分支名
    ```

  - ```
    如果拉取不成功, 请先执行 git fetch
    原因
    1, 远程没有该分支
    2, git branch -r 查看本地缓存的所有远程分支, 远程分支名不在本地缓存里, 故报错
    ```

  

