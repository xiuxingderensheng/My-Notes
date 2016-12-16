# git tutorial
##基本操作##

1)
```
git init
```
创建一个git仓库。

2)
```
git status
```
查看仓库状况。

3)
```
git add Afile Bfile
```
添加到临时存储空间。

4)
```
git commit -m "status"
```
提交到仓库。

5)
```
git push
```
提交到github。


##更新远程代码到本地##

1)查看远程分支。
```
git remote -v
```

2)从远程获取最新分支到本地。
```
git fetch origin master:temp
```
从远程的origin仓库的master分支下载到本地并新建一个分支temp。

3)比较本地仓库和远程参考的区别。
```
git diff temp
```

4)合并temp分支到master分支。
```
git merge temp
```
合并的时候可能会出现冲突，需要处理。

5)如果不想要temp分支，可以删除此分支。
```
git branch -d temp
```
如果该分支没有合并到主分支会报错，可以用 git branch -D <分支名> 强制删除。

或者可以采用下面的方式：

```
git remote -v

git fetch origin master

//比较远程参考和本地仓库
git log -p master..origin/master

git merge origin/master
```

