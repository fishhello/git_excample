:chestnut:**git使用中出现的问题**:chestnut:

ps:[github使用的图标](https://segmentfault.com/a/1190000009649780#articleHeader6)

### 1.每次push推送给远程仓库都需要手动输入github账号密码 :sun_with_face:
&emsp;[stackoverflow](https://stackoverflow.com/questions/8588768/git-push-username-password-how-to-avoid)
```
git remote set-url origin git+ssh://git@github.com/username/reponame.git
```

### 2.使用git status等命令显示含中文的文件错误 :sun_with_face:
&emsp;[Git实用小技巧：git status 中文文件名编码问题解决](https://blog.csdn.net/MLQ8087/article/details/52174834)
```
git config --global core.quotepath false
```
