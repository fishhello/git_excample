&emsp;本地仓库的使用

### 1.生成本地的公钥
```
//一路回车
ssh-keygen -t rsa -C "2874497884@qq.com"
```

### 2.设置一个邮箱和用户名--在github中显示代码的上传者
```
git config --global user.name "fish" //设置用户名
git config --global user.email "2874497884@qq.com" //设置邮箱
```

### 3.初始化一个本地仓库
&emsp;当前目录生成.git目录--记录版本等信息
```
git init
```

### 4.查看远程仓库的名字
&emsp;默认是origin  --提交代码时需要指定仓库提交
```
git remote
```

### 5.跟踪修改的文件(添加进暂存区)
```
git add xxx(文件)
```

### 6.查看文件的状态
&emsp;modified--对原来的文件进行过修改的、untracked--新写的文件没添加到暂存区的
```
git status
```

### 7.提交到本地仓库
```
git commit -m "填写本次提交的说明"
```

### 8.提交到远程仓库
&emsp;push几个命令的差别 from [水木神州10](https://www.cnblogs.com/zhouj850/p/7260558.html)
```
git push origin master|你需要提交的分支
```

## 9.使用分支
&emsp;假设你准备开发一个新功能，但是需要两周才能完成，第一周你写了50%的代码，如果立刻提交，由于代码还没写完，不完整的代码库会导致别人不能干活了。如果等代码全部写完再一次提交，又存在丢失每天进度的巨大风险，怎么办？

&emsp;你可以创建一个属于自己的分支，别人看不见，还继续在原来的分支上工作，而你在自己的分支上进行开发，等开发完毕，合并即可

### 10.创建分支
&emsp;创建后进入新建分支
```
git checkout -b dev|自定义分支名

等于执行了:
git branch dev|自定义分支名
git checkout dev|自定义分支名
```

### 11.查看当前的分支
```
git branch
```

### 12.分支注意
**在当前分支上进行add、commit操作后要回到主分支(master)合并**
**只有主分支才能进行合并分支、推送(push)等操作**

### 13.切回主分支(master)
```
git checkout master
```

### 14.删除分支
```
git checkout -d dev|自定义的分支名
```
