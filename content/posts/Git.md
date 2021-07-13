---
title: "Git常用命令收集"
date: 2020-02-03T17:31:36+08:00
draft: false
---

### 本文用来收录我自己用过的好用的 git 命令



#### 分支操作

---

```bash
# 新建一个分支，但不切换到这个新建的分支
git branch <branch>

# 新建一个分支，并且切换到这个新建的分支
git checkout -b <branch>

# 新建一个分支，指向指定 commit
git branch <branch> <commit>

# 新建一个分支，与指定的远程分支建立追踪关系
git branch --track <branch> <remote-branch>
git branch -t <branch> <remote-branch>

# 切换到指定分支，并更新工作区
git checkout <branch>

# 让本地分支追踪某一远程分支
git branch --set-upstream <branch> <remote-branch>
git branch --set-upstream-to=<remote-branch>  <branch>

# 合并指定分支到当前分支
git merge [branch]

# 合并某分支到某分支
git merge <from-branch> <to-branch>

# 选择一个commit，合并进当前分支
git cherry-pick <commit>

# 删除分支
git branch -d <branch>

# 删除远程分支
git push origin --delete <branch-name>
git branch -dr <remote/branch>
```



#### 标签操作

---

```bash
# 列出所有 tag
git tag

# 在当前 commit 新建一个 tag
git tag 

# 在指定 commit 新建一个 tag
git tag <tag> <commit>

# 删除本地 tag
git tag -d <tag>

# 删除远程 tag
git push origin :refs/tags/<tagName>

# 查看 tag 信息
git show <tag>

# 提交指定 tag
git push <remote> <tag>

# 提交所有 tag
git push <remote> --tags

# 新建一个分支，指向某个tag
git checkout -b <branch> <tag>
```



#### git拉取远程分支并切换到该分支

---

整理了五种方法，我常用最后一种，这五种方法（除了第4中已经写了fetch的步骤）执行前都需要执行git fetch来同步远程仓库

（1）git checkout -b 本地分支名 origin/远程分支名

（2）git checkout --track origin/远程分支名 （这种写法是上面的简化版，效果完全一样）

（3）git checkout -t origin/远程分支名（这种写法是2的简化版）

（4）fetch指定的一个分支：

​		  git fetch [repo] [remote_branch_name]:[local_branch_name]

​		  git checkout [local_branch_name]

​		（第一行的:[local_branch_name]如果不写，则本地新建的分支名默认与远程分支名相同）

（5）git fetch 获取远程所有分支

​		  git branch -r 可以看到所有远程分支，假设有一个分支叫origin/mybranch

​		  git checkout mybranch 即可，会在本地新建一个同名分支，并与该远程分支关联

​		（git checkout origin/mybranch 会进入detached head状态，不会在本地新建分支，不要这样写）