![Git分区](C:\Users\Administrator\Desktop\Git分区.jpg)

# 本地工作详解

工作区 是对于项目的某个版本提取出来的内容。

暂存区是一个文件，保存了下次要提交的文件列表信息。

本地库是 Git 用来保存项目的元数据对象和对象数据库的地方。

# Git 基础

## 三种状态

1. 已经提交 committed	提交到本地库

2. 已修改 modified  在工作区修改未提交

3. 已暂存 staged  在暂存区未提交到本地库

   `git status` 查看那些文件处于那些状态

## 获取 Git 项目仓库的方式

1. 将尚未进行版本控制的本地目录转化为 Git 仓库
2. 从其他服务器克隆一个已存在的 Git 仓库

### 在已经存在的目录中初始化仓库

`git init`

### 忽略文件

自动生成文件无需纳入 Git 管理

可以创建一个名为 .gitignore 的文件，列出要忽略的文件

`cat .gitigore`
`*.[oa]`	.o 或 .a 一般都是编译过程出现的文件

`*~` 许多编辑软件用以~结尾的文件保存副本

可能还要忽略log，tmp 或者 pid 目录等等

### git commit -a

自动把所有已经跟踪过的文件暂存起来一并提交，跳过 git add

### git rm -cached <files>

删除本地库但是保留在磁盘

### git checkout  -- <file>

Git 会用最近提交的版本覆盖他

### git fetch <remote>

将数据下载到本地仓库，不会自动合并或修改当前的工作

### git push <remote> <branch>

推送到远程仓库



# Git 配置用户签名

标识用户

(单个仓库有效)

```
git config user.name 用户
git config user.email 邮箱
```

(全局有效) 推荐

```
git config --global user.name 用户
git config --global user.email 邮箱
```

# Git 查看状态

```
git status
```

# Git 添加到暂存区

添加 文件到暂存区

```
git add [file] [file2] ...
```

添加目录到暂存区

```
git add [dir]
```

添加所有文件到暂存区

```
git add .
```

# Git 提交代码

将暂存区文件提交到本地仓库

```
git commit -m [备注信息]
```

提交指定文件

```
git commit [file] [file2] .. -m [备注信息]
```

直接提交(文件被修改后不需要执行 git add)

```
git commit -am [备注信息]
```

# Git 版本切换

```
git reflog 			查看提交信息和版本号
git log			 查看详细信息
```

切换 版本

```
git reset --hard 版本号 
```

# Git 分支

```
git branch -v		查看分支
git branch 分支名		创建分支
git branch -d 分支名		删除分支
git branch -m 分支名 新分支名 		修改分支名字
git checkout 分支名		切换分支
git merge 分支名		合并分支(目标分支合并到当前分支)
```

# Git 合并分支冲突

合并分支时, 两个分支在同一个代码的同一个位置都有修改,Git无法判断,需要手动修改后 再次提交

冲突时的状态

![image-20220801194706234](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220801194706234.png)

```
修改后 执行
git commit -m 'merge commit'
```

