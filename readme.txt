Git is a version control system
Git is free software

The second add.

GPL

Git has a mutable index called stage.

Git tracks changes of file.
在本地仓库目录下打开Git Bash here，然后通过命令行将本地仓库与远程仓库关联：
    git remote add origin git@github.com:moonoff/learngit.git
将本地add，提交之后的内容推送到远程仓库：
    第一次：git push -u origin master
    之后  ：git push origin master

克隆远程仓库：
    git clone git@github.com:moonoff/getskills.git


1.创建分支：
    git checkout -b dev
    -b 参数表示：创建分支，并且切换分支：
                $ git branch dev
                $ git checkout dev
2.查看分支：
    git branch
3.合并分支：将dev分支合并到master：
    git checkout master  （指定当前分支）
    git merge dev        （合并dev到当前分支）
4.删除分支：
     git branch -d dev

5.解决冲突：
    解决方法：合并之后提示冲突文件，打开文件修改成最终保存结果，使用add，commit命令交
    git log --graph --pretty=oneline --abbrev-commit（查看分支合并情况）

6.分支管理策略：