

# 工作区、暂存区、版本库

![image-20230811153429554](C:\Users\ccc\AppData\Roaming\Typora\typora-user-images\image-20230811153429554.png)



# 上传本地文件到版本库

```
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/sblk0402/testgit.git
git push -u origin main
```

鼠标右键，使用Git Bash Here 打开



![](https://img-blog.csdnimg.cn/7a866bafa2734a6eb772c3e0c7bb60a2.png)

* 使用当前目录作为 Git 仓库，我们只需使它初始化。该命令执行完后会在当前目录生成一个 .git 目录。

```
get init
```

* 使用我们指定目录作为Git仓库。会在当前文件夹内新建文件夹newrepo，并创创建仓库

```
git init newrepo
```

如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：

添加所有文件名以'.c'结尾的文件

```
git add *.c
```

添加当前文件夹下所有文件

```
git add .
```

提交暂存区到本地仓库

```
git commit -m '初始化项目版本'
```

选择上传的分支

```
git branch -M main
```

和远程仓库连接,xxxxx为自己的GitHub名，test 为仓库名。

```
git remote add origin https://github.com/xxxxx/test.git
```
 将本地项目推送到远程仓库

```
git push -u origin main
```

# git配置

git 的设置使用 **git config** 命令。

显示当前的 git 配置信息：

```
$ git config --list
credential.helper=osxkeychain
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
```

编辑 git 配置文件:

```
$ git config -e    # 针对当前仓库 
```

![image-20230811153925548](C:\Users\ccc\AppData\Roaming\Typora\typora-user-images\image-20230811153925548.png)

或者：

```
$ git config -e --global   # 针对系统上所有仓库
```

![image-20230811154044259](C:\Users\ccc\AppData\Roaming\Typora\typora-user-images\image-20230811154044259.png)

设置提交代码时的用户信息：

```
$ git config --global user.name "runoob"
$ git config --global user.email test@runoob.com
```

如果去掉 **--global** 参数只对当前仓库有效。

# Git 基本操作

Git 的工作就是创建和保存你项目的快照及与之后的快照进行对比。

本章将对有关创建与提交你的项目快照的命令作介绍。

Git 常用的是以下 6 个命令：**git clone**、**git push**、**git add** 、**git commit**、**git checkout**、**git pull**，后面我们会详细介绍。

![img](https://www.runoob.com/wp-content/uploads/2015/02/git-command.jpg)

**说明：**

- workspace：工作区
- staging area：暂存区/缓存区
- local repository：版本库或本地仓库
- remote repository：远程仓库

一个简单的操作步骤：

```
$ git init    
$ git add .    
$ git commit  
```

- git init - 初始化仓库。
- git add . - 添加文件到暂存区。
- git commit - 将暂存区内容添加到仓库中。

### 创建仓库命令

下表列出了 git 创建仓库的命令：

| 命令        | 说明                                   |
| :---------- | :------------------------------------- |
| `git init`  | 初始化仓库                             |
| `git clone` | 拷贝一份远程仓库，也就是下载一个项目。 |

------

## 提交与修改

Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。

下表列出了有关创建与提交你的项目的快照的命令：

| 命令         | 说明                                     |
| :----------- | :--------------------------------------- |
| `git add`    | 添加文件到暂存区                         |
| `git status` | 查看仓库当前的状态，显示有变更的文件。   |
| `git diff`   | 比较文件的不同，即暂存区和工作区的差异。 |
| `git commit` | 提交暂存区到本地仓库。                   |
| `git reset`  | 回退版本。                               |
| `git rm`     | 将文件从暂存区和工作区中删除。           |
| `git mv`     | 移动或重命名工作区文件。                 |

### 提交日志

| 命令               | 说明                                 |
| :----------------- | :----------------------------------- |
| `git log`          | 查看历史提交记录                     |
| `git blame <file>` | 以列表形式查看指定文件的历史修改记录 |

### 远程操作

| 命令         | 说明               |
| :----------- | :----------------- |
| `git remote` | 远程仓库操作       |
| `git fetch`  | 从远程获取代码库   |
| `git pull`   | 下载远程代码并合并 |
| `git push`   | 上传远程代码并合并 |
