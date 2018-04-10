&emsp;git多人协作

流程:
&emsp;首先，可以试图用git push origin branch-name推送自己的修改。

&emsp;如果推送失败，则因为远程分支比你的本地更新早，需要先用git pull试图合并。

&emsp;如果合并有冲突，则需要解决冲突，并在本地提交。再用git push origin branch-name推送。
