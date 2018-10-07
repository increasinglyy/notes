git分支管理（branch、checkout、merge）

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`

创建+切换分支：`git checkout -b <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

------



1、master指向提交，HEAD指向当前分支（master）。

![](images/0.png)

2、当创建新的分支dev，新建指针dev 指向master相同的提交，再把HEAD指向dev（当前分支）。

```
$ git checkout -b dev
Switched to a new branch 'dev'
```

`git checkout`命令加上`-b`参数表示创建并切换。相当于，

```
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

![](images/1.png)



3、之后commit提交就是针对dev分支。

![](images/2.png)

4、`dev`分支的工作完成，切换回`master`分支：（HEAD指向当前分支）

```
$ git checkout master
Switched to branch 'master'
```

![](images/3.png)



5、合并分支。

```
$ git merge dev
```

![](images/4.png)

6、删除分支

```
$ git branch -d dev
```



# 多人协作的工作模式

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图**合并**；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

 如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

如：

没有指定本地`dev`分支与远程`origin/dev`分支的链接，根据提示，设置`dev`和`origin/dev`的链接：

```
$ git branch --set-upstream-to=origin/dev dev
```



# git标签管理（tag）

标签是指向某个commit的指针

`git tag v1.0`  用于新建一个标签，默认为`HEAD`，也可以指定一个commit id；

`git tag -a <tagname> -m "blablabla..."`可以指定标签信息；

`git tag`可以查看所有标签。



