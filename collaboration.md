&emsp;git多人协作

流程:
&emsp;首先，可以试图用git push origin branch-name推送自己的修改。

&emsp;如果推送失败，则因为远程分支比你的本地更新早，需要先用git pull试图合并。

&emsp;如果合并有冲突，则需要解决冲突，并在本地提交。再用git push origin branch-name推送。

REF:
[使用GitHub进行团队合作](http://xiaocong.github.io/blog/2013/03/20/team-collaboration-with-github/)

[Git教程之一个团队如何在github上协作开发](https://blog.csdn.net/gpwner/article/details/53140016)
