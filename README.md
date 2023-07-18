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
`git remote add origin git@github.com:michaelliao/learngit.git`
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
which echo可以查看（到底是如何查找到环境变量再调用的）
mv f2 f1(相当于是重命名)
cp f2 f2.bak（相当于备份）
__find的一些进阶用法：__
find a.cpp(精确查找)
find . | grep hello（在该目录底下寻找所有带hello关键词的东西）
__chmod可以更改一些权限:__
chmod +r `script.sh`（给所有人增加read的权限）
chmod -r `script.sh`
chmod 777 `public.py`（让文件可以被任何人去读写执行）
chmod o-rw journal.txt（禁止组外的用户的读写）
__关于一些帮助__
man ls（/-a）
tldr ls
__配置公钥私钥__
等有了服务器再说吧
__关于vimtutor的用法__
vimtutor -g zh
vimtutor 自学一手
## 有关web容易遗忘的知识点和标签
__关于一些比较常用却容易忘记的标签__
hr标签：水平线（其中的属性有size,color）
br标签：换行
b、i：分别对应了加粗或者是斜体
__关于a标签的用法__
href="https://www.runoob.com/" 
target="_blank"
id="tips"
href="#tips"（实现定向的跳转） 
__在head标签中__
base标签：定义了基本的链接地址，与链接目标
base href="http://www.runoob.com/images/" target="_blank"
link标签：链接到样式表格
link rel="stylesheet" href="mystyle.css"
style标签：可以直接添加基本样式来对文档进行渲染
meta标签：描述了一些基本的元数据
meta name="keywords" content="HTML, CSS, XML, XHTML, JavaScript"（这里为搜索引擎定义了关键词）
meta name="description" content="免费 Web & 编程 教程"（这里是为了网页的定义来描述了内容）
meta name="author" content="Runoob"（网页作者）
__关于字体颜色背景颜色等等的基本样式操作__
style="color:red;font-size:20px;margin-left:20px"把字体颜色搞成蓝色，大小调整，并且前面空出一些格子来
style="background-color:red;"这个是把背景颜色搞成红色
style="text-align:center;font-family:arial;"居中，字体黑体
__关于图像__
img border="10" src="pulpit.jpg" alt="Pulpit rock" width="304" height="228"(很容易不做解释)
####很难的一个东西：创造图像映射（目前先跳过一下）
__表格__
table做标签（一般有以下几个东西：thead,tr,td）
table做标签，内部添加属性cellpadding可以使得表格单元格内容与单元格边框间有一定的边距
table做标签，内部添加属性cellspacing可以使单元格间有一定的边距(等于0去掉相同的border线)
在tr中可以写三个th
在tr中也可以写一个th 若干个td（完成水平表格和竖直表格两种方式）
caption标签可以显示表标题
如果需要合并单元格利用colspan="2"或者rowspan="3"即可
__列表__
ul>li*3
ol>li*3
无序列表以及有序列表生成的快捷键
style="list-style-type:disc"通过这种方式改变标号的格式
__表单__
(form action="")
Username: (input type="text" name="user")
没什么特别的，name用作唯一标识，value是给服务器的值
Password: (input type="password" name="password")
(/form)
(form action="")
(input type="radio" name="sex" value="male")男
(input type="radio" name="sex" value="female")女
(/form)
当然如果这边的radio变成checkbox我们就变成了复选框
__注释的基本写法__
<"!--blabla--">这是注释的写法（其中双引号是不需要的）


