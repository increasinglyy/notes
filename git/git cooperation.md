# git cooperation

## git上fork别人仓库后同步更新

`git remote -v`

`git remote add upstream git@github.com:xxx/xxx.git`  进入自己的项目，配置remote，指向原来的仓库(upstream)

（同步更新）

`git remote -v`

`git fetch upstream`  拉取下upstream，从原仓库同步更新

（`git checkout master`  切换到本地分支主干)

`git merge upstream/master`  合并到本地代码

`git push origin master`  将本地修改推到远程fork仓库