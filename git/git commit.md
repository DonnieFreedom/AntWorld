# git commit

- `git commit -m ''` 提交到本地仓库

- 修改最后一次提交的日志 且未push

  ```
  git commit --amend
  ```

- 修改最后一次提交且已push到服务器

   ```
   git commit --amend
   git push origin master --force
   # 此操作会导致别人无法同步
   ```

  
