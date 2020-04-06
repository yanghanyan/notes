Git常用命令
===============

<!-- GFM-TOC -->
* [1、常用命令](#1常用命令)
* [2、分支](#2分支)
* [3、推送](#3推送)
* [4、拉取](#4拉取)
* [5、合并及回退](#5合并及回退)
* [6、SSH秘钥](#6SSH秘钥)
<!-- GFM-TOC -->

#### 1、常用命令

- 初始化：
```bash
  git init
```

- 设置用户名
```bash
  git config --global user.name "username"
```

- 设置用户邮箱
```bash
  git config --global user.email "xxx@mail.com"
```

- 设置用户密码
```bash
  git config --global user.password "password"
```

- 查看配置
```bash
  git config --list
```

- 克隆远端项目
```bash
  git clone https://...
```

- 克隆指定xxx分支远端项目
```bash
  git clone -b xxx https://...
```

- 进入/返回目录
```bash
  cd ..
  cd directory
```

- 查看文件更改状态：
```bash
  git status
```

- 添加所有更改至暂存区
```bash
  git add ./
```

- 添加指定更改文件至暂存区
```bash
 git add ./derectory/xxx.java
```

- 提交暂存区至本地仓库
```bash
  git commit -m '提交说明'
```

- 提交所有更改内容
```bash
  git commit -a
```

- 覆盖上一个提交
```bash
  git commit --amend
```

#### 2、分支

- 查看所有本地、远端分支
```bash
  git branch -a
```

- 查看远端分支
```bash
  git branch -r
```

- 切换到xxx分支
```bash
  git checkout xxx
```

- 新建xxx分支并切换至该分支
```bash
  git checkout -b xxx
```

- 删除xxx分支
```bash
  git branch -d xxx
```

- 获取远端分支的所有更新
```bash
  git fetch --all
```

- 设置远端仓库地址
```bash
  git remote add origin https://...
```

- 新增远端仓库xxx分支
```bash
  git remote add xxx https://...
```

- 解除远端仓库
```bash
  git remote remove origin
```

- 删除远端xxx分支
```bash
  git push origin --delete xxx
```

- 查看当前远端仓库地址
```bash
  git remote -v
```

#### 3、推送

- 推送至已绑定的远端分支
```bash
  git push
```

- 关联远端xxx分支并推送
```bash
  git push --set-upstream origin xxx
```

- 推送至远端xxx分支
```bash
  git push origin xxx
```

- 推送本地xxx分支至远端yyy分支
```bash
  git push origin xxx:yyy
```

- 推送本地所有分支至远端
```bash
  git push --all origin
```

#### 4、拉取

- 更新拉取已绑定的远端分支
```bash
  git pull
```

- 更新拉取远端xxx分支
```bash
  git pull origin xxx
```

- 强制覆盖更新(会覆盖本地所有未推送改动，慎用)
```bash
  git fetch --all
  git reset --hard origin/xxx
```

#### 5、合并及回退

- 合并xxx分支至当前分支
```bash
  git merge xxx
```

- 中止合并
```bash
  git merge --abort
```

- 将未提交的变化移除
```bash
  git stash
```

- 将移除的变化恢复
```bash
  git stash pop
```

- 回退到上一次提交的复活点
```bash
  git reset --hard ORIG_HEAD
```

- 回退至上一个版本
```bash
  git reset HEAD~
```

- 回退至上n个版本
```bash
  git reset HEAD~...~
```

- 取消暂存文件(用于后悔add命令)
```bash
  git reset HEAD xxx.class
```

- 回退commit(会保留commit前的文件)
```bash
  git reset --soft HEAD^
```

#### 6、SSH秘钥

- 生成SSH秘钥对
```bash
  ssh-keygen -t rsa -C "username or email"
```

- 查看生成的秘钥对
```bash
  cat ~/.ssh/id_rsa.pub
```
