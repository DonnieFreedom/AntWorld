# git checkout

- `git checkout next_branch` 切换分支

- `git checkout -b next_branch` 创建并切换分支

- git checkout 时出现error: your local changes .......

  ```
  有3种解决办法
  1` git reset --hard HEAD (如果你不介意失去那些微小变化)
  2` checkout -f (丢弃本地更改, )
  3` git stash进行存储
      git stash save
      git checkout branch
      // do something
      git checkout oldbranch
      git stash pop # 恢复最近的缓存到当前文件中，同时删除恢复的缓存条目。
      # git stash list  # 指令，查看本地当前的缓存列表
      # git stash apply stash@{id} # 恢复指定id的stash内容，同时不会删除恢复的缓存条目。
  4` git add . && git commit 
  ```

  

