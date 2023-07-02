 # 基础知识入门
## GIT
__新建立一个仓库并且进入仓库并初始化：__
mkdir learngit
cd learngit
git init

__查看一些基本信息：__
git config --list
pwd
git config user.email

__新建立一个文档：__
touch README.txt
git add README.txt
git commit -m"write a README file"

touch file1.txt
touch file2.txt
git add file1.txt
git add file2.txt
git commit -m"add two files"
上面的操作是一口气增加了两个

__查看状态以及不同的内容:__
git status
git diff README.txt
修改完之后当然还是需要用add，commit进行一个保存啦

__进行一个时光机的穿梭__
git log --pretty=oneline(这边是用于查看各类ID信息)
git reset --hard HEAD^（回退到前一个版本）
cat README.txt（可以进行查看）
git reflog(进行一个势头的回流)
git reset --hard 792538(进行一个未来定向的穿梭)

__如何进行修改撤销__
1、在工作区还没add到暂存区：
git checkout -- HEAD README.txt
2、已经add到了暂存区但是还没有commit:
git reset HEAD README.txt
git status(仅仅是查看以下，确保暂存区里面没东西了)
git checkout -- README.txt(再用之前删除工作区域的方法即可)

__如何进行文件的删改__
rm test.txt（工作区和版本库不一致）
情况一：
git rm test.txt
git commit -m"remove test.txt"
(确实要从版本库中把该文件删去)
情况二：
git checkout --test.txt
(误删，可以用这种方式来进行还原)

__远程库的添加与克隆__
添加：
`git remote add origin git@github.com:michaelliao/learngit.git`--
`git push -u origin master`
（根据命令按要求复制）
克隆：
`git clone git@github.com:michaelliao/gitskills.git`
（打开code那一栏的地址克隆即可）
__如果我们需要复制远程仓库到自己的仓库，需要选择FORK即可__

__分支管理__
1、创建，切换，合并,删除：
git branch dev
git checkout dev
git merge dev
git branch -d/D dev
git branch(查看)
2、禁用fast forward
git merge --no-ff -m "merge with no-ff" dev
3、查看所有分支历史信息
git log --graph --pretty=oneline --abbrev-commit
4、工作区隐藏
git stash
git stash list

git stash apply stash@{0}
git stash drop
or
git stash pop 

##Linux入门