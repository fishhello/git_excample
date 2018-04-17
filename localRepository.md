
&emsp;本地仓库的使用

流程:
1.前期准备:项目负责人在服务器或者github上创建一个仓库->添加Collaborators->设定分支、项目分工...

2.开发人员clone远程仓库到本地

3.工作区(打代码)->add(暂存区)->commit(本地仓库)->pull(本地仓库同步远程仓库)->push(提交到远程仓库)->end

### 1.初始化仓库
#### 第一种
- 生成本地仓库(.git目录)
 ```
git init
 ```

- 使用remote关联远程仓库(需要先创建本地仓库)
 ```
git remote add github git@github.com:fishhello/git_excample.git
 ```

#### 第二种
- 待补充
 ```
git init --bare
 ```

#### 第三种
- 在本地clone远程仓库
 ```
git clone https://github.com/fishhello/git_excample.git
 ```

- [码云使用](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00150154460073692d151e784de4d718c67ce836f72c7c4000)

### 2.查看远程仓库的名字
&emsp;默认是origin  -->如果关联了github的仓库->远程库的名称叫github     如果关联了码云的仓库->远程库的名称叫gitee
```
git remote
```

### 3.跟踪修改的文件(添加进暂存区)
```
git add xxx(文件1) xxx(文件2)
```

### 4.查看文件的状态--忘记命令就先打这个看看再说
&emsp;modified--对原来的文件进行过修改的、untracked--新写的文件没添加到暂存区的
```
git status
```

### 5.提交到本地仓库
&emsp;每commit一次提交到本地仓库都可以当添加了一个新的版本,也会生成一个唯一的commit_id绑定当前的commit(实现版本回退)
```
git commit [file] -m "填写本次提交的说明"
```

### 6.撤销操作
&emsp;HEAD表示本地仓库中的最新版本

- 从暂存区中撤销
```
git reset HEAD file
```

- 撤销对工作区文件的修改
```
git checkout -- file
```

- 版本回退--更改本地仓库
&emsp;HEAD表示当前的版本(最新一次的commit),上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
```
git reset --hard commit_id
```

- 如何查看commitID？

  - 查看提交历史
 ```
git log --pretty=oneline
 ```

  - 查看命令历史
 ```
git reflog
 ```

### 7.提交到远程仓库--[多人协作会有冲突](https://github.com/fishhello/git_excample/blob/master/collaboration.md)
&emsp;push几个命令的差别 from [水木神州10](https://www.cnblogs.com/zhouj850/p/7260558.html)
```
git remote    //查看远程仓库名
git push 仓库名(origin) master|你需要提交的分支
```

## 8.使用分支
&emsp;假设你准备开发一个新功能，但是需要两周才能完成，第一周你写了50%的代码，如果立刻提交，由于代码还没写完，不完整的代码库会导致别人不能干活了。如果等代码全部写完再一次提交，又存在丢失每天进度的巨大风险，怎么办？

&emsp;你可以创建一个属于自己的分支，别人看不见，还继续在原来的分支上工作，而你在自己的分支上进行开发，等开发完毕，合并即可

### 9.创建分支
&emsp;创建后进入新建分支
```
git checkout -b dev|自定义分支名

等于执行了:
git branch dev|自定义分支名
git checkout dev|自定义分支名
```

### 10.查看当前的分支
```
git branch
```

### 11.分支注意
**在当前分支上进行add、commit操作后要回到主分支(master)合并**
**只有主分支才能进行合并分支、推送(push)等操作**

### 12.切回主分支(master)
```
git checkout master
```

### 13.合并分支
```
git merge 需要合并的分支
```

### 14.删除分支
```
git checkout -d dev|自定义的分支名
```
