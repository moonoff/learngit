pwd （显示当前目录）
git init （在当前文件夹下生成git 仓库）
git add <文件名> （将文件添加到缓存区）
git commit -m "形容本次提交的文字"    （将缓存区的内容正式加入仓库）
git status   （仓库状态，是否有更新文件未添加）
git diff readme.txt  （查看修改内容）
git log (提交说明)
git reset --hard <commit id>   (将版本回退到commit id版本)
git reflog (记录每一次commit的)


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
    git merge --no-ff -m "merge with no-ff" dev （保留分支合并路径）

7.bug分支：
     git stash（将当前的未完成工作暂存起来，去修改bug）
     git stash list（暂存列表）
     git stash apply （恢复暂存内容）git stash drop（删除暂存列表）
     git stash pop （恢复暂存内容，并删除列表）
     git stash apply stash@{0}（指定恢复的列表）

8.新功能开发分支：
    git branch -D dev (如果新功能不开发了，准备删除，使用-d无法删除没有合并的分支)

9.推送分支：
    git push origin <分支名>

10.多人协作：
    伙伴A克隆：git clone git@github.com:moonoff/learngit.git   (只有master分支)
    伙伴B创建分支：git checkout -b dev origin/dev
    伙伴C要提交分支dev，冲突发生，可以使用git pull，如果失败：
    建立本地dev与远程dev连接：git branch --set-upstream dev origin/dev  接着 git pull

11.标签
    打印标签：
        git tag v1.0 (默认打印的标签在最新提交的coommit上)
        git tag v0.9 <commit id> (将标签打印在commit id的那次提交上)
        git tag -a v0.1 -m "version 0.1 released" <commit id> 

    操作标签：
        git tag -d v0.1
        git push origin v1.0    （推送标签）
        git push origin --tags  (推送所有未推送的标签)
    删除远程标签：
        1. 先删除本地标签
        2. git push origin :refs/tags/v0.9

