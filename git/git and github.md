# git & github

1. cd到版本库（仓库）目录，如PAT

2. `$ git init`（会显示一个master）

3. 在PAT文件夹中添加各种文件，如readme.md

4. `$ git add readme.md` 把文件添加到仓库

   `$ git add .`  添加所有修改

5. `$ git commit -m "wrote a readme file"` 把文件提交到仓库

6. [远程仓库添加 SSH Key](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000)

7. 登录GitHub，创建与本地git同名的仓库  --->进行两个仓库远程同步

8. `$ git remote add origin git@github.com:increasinglyy/PAT.git`关联仓库

9. `$ git push -u origin master` 本地库的所有内容推到远程库（第一次推加 -u）以后是 `$ git push origin master`

10. `$ git clone git@github.com:increasinglyy/PAT.git` 从远程库克隆（直接cd 到需要克隆的文件夹下）



## others

1. `$ git status` 查看状态

2. `$ git diff` 查看不同

3. `$ git log` 查看提交历史

4. `$ git rm test.txt` 从版本库中删除文件（status提示已经在文件管理器中删除，且确实要从版本库中删除）

   `$ git checkout -- test.txt` 删错了，从版本库中恢复

