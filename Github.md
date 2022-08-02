# 创建别名

```
查看
git remote -v
创建
git remote add <name> <地址>
```

# GitHub 推送本地库

```
git push <别名> <分支名>
```

# GitHub 拉取远程库

```
git pull <别名> <分支名>
```

# GitHub 克隆远程库

```
git clone <远程地址>
```

# GutHub 免密登录

1.找到windwos下用户下的.ssh文件

2.生成密钥

```
ssh-keygen -t rsa -C <帐号>
```

3.复制公钥 id_rsa.pub

4.配置GitHub 中的配置