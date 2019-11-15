---
title: git总结
abbrlink: d9ac2aad
date: 2018-08-28 21:01:40
---

###  1先在码云官网创建自己的项目

略

### 2在桌面 拉去远端码云项目到本地:

```vim
git clone https://gitee.com/edward_h/OnlineEducation.git
```

### 3新建分支,并关联远程分支方便以后上传项目文件,注意 有些个性化配置需要上传,比如vue项目的 node_modules

```
 git checkout -b dev    # 创建分支并切换到该分支
```

### 切换分支   （dev是分支名)

```vim
git checkout dev    # 切换分支   （dev是分支名)  #这步不用建立分支了
```

### 查看分支

```
git branch
```

### 4.创建远程分支连接(此处为master分支)

```
git branch --set-upstream-to=origin/master
```

如果提示错误,则说明远程没有该分支,则需要创建该远程分支

创建完毕后,再执行4操作,关联远程分支

### 5.执行添加项目操作,这两步操作必须同时存在

```vim
git add -A 文件名   :添加修改文件 

git commit -m "提交的信息"  将文件存进暂存区 
```

### 6.此处拉下文件如果提示冲突,则解决完冲突,再次执行第五步操作,因为修改了冲突的代码,所以重新将代码添加到暂存区

```
git pull     # 下拉最新文件
```

```vim
git add  文件名    
git add -A 提交所有修改

git commit -m "提交的信息" 

```

### 7.直到不显示冲突则说明解决完冲突了,再提交

```
git push    # 上传文件
```

不提示错误,则上传完毕

### 8.可以查看上一次的修改操作是什么

```vim
git status
```





### 备用知识点 建项目着 如果想让其他人通过输入账号密码才能上传文件 则输入如下命令  (这些命令用不到)

插入如下代码使项目中的组员每次修改数据都要输入账号和密码：

- git config --global user.name [username]
- git config --global user.password [userpassword]
- PS：想要保存密码，则需要插入如下代码： git config –global credential.helper store。



###gitee推送到远程仓库时提示错误

remote: Incorrect username or password ( access token )

fatal: Authentication failed for 'https://gitee.com/***/***.git/'

解决办法：清除本地的gitee用户名和密码

git config --system --unset credential.helper

再执行推送，重新输入用户名和密码。













