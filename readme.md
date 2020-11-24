#github笔记
#
#1.设定GitHub
要使用GitHub，首先需要创建SSH Key，SSH将用来加密本机与远端服务器之间的通信，同时也是识别你对代码所做的变更的方法。
SSH Key可以使用Git命令行来产生，如果你已经有一个SSH Key，那么在这里也可以直接使用。
要使用Git创建SSH Key 首先需要打开Git Bash 命令行，输入命令：
ssh-keygen  -C  "username@email.com"  -t  rsa
说明：username@email.com 需要更换成你自己的email地址
程序将提出一些问题，接受文件默认存放位置，当要求输入pass phrase时，如果本机安全没有问题，也可以不输入。找到当时制定的文件存储位置中id_rsa.pub文件，这就是在GitHub上申请帐户时需要使用的SSH公钥文件。
在github.com的register中选择Free account，在后续的界面中按照要求填入相应的内容即可完成注册，很简单的。

#2.Git 命令初识

在正式介绍Git命令之前，先介绍一下Git 的基本命令和操作，对Git命令有一个总体的认识

示例：从Git 版本库的初始化，通常有两种方式：

1）git clone：这是一种较为简单的初始化方式，当你已经有一个远程的Git版本库，只需要在本地克隆一份

例如：git  clone  git://github.com/someone/some_project.git   some_project 

上面的命令就是将'git://github.com/someone/some_project.git'这个URL地址的远程版本库，完全克隆到本地some_project目录下

git clone git@github.com:antknox/Project-hosts-download-share.git /d/git

2）git init 和 git remote：这种方式稍微复杂一些，当你本地创建了一个工作目录，你可以进入这个目录，使用'git init'命令进行初始化；Git以后就会对该目录下的文件进行版本控制，这时候如果你需要将它放到远程服务器上，可以在远程服务器上创建一个目录，并把可访问的URL记录下来，此时你就可以利用'git remote add'命令来增加一个远程服务器端，
例如：git  remote  add  origin  git://github.com/someone/another_project.git
上面的命令就会增加URL地址为'git: //github.com/someone/another_project.git'，名称为origin的远程服务器，以后提交代码的时候只需要使用 origin别名即可

cd Project-hosts-download-share
git init
git remote add origin git@github.com:antknox/Project-hosts-download-share.git

#3.Git 常用命令

1) 远程仓库相关命令
检出仓库：        $ git clone git://github.com/jQuery/jquery.git
查看远程仓库：$ git remote -v
添加远程仓库：$ git remote add [name] [url]
删除远程仓库：$ git remote rm [name]
修改远程仓库：$ git remote set-url --push [name] [newUrl]
拉取远程仓库：$ git pull [remoteName] [localBranchName]
推送远程仓库：$ git push [remoteName] [localBranchName]

*如果想把本地的某个分支test提交到远程仓库，并作为远程仓库的master分支，或者作为另外一个名叫test的分支，如下：
$git push origin test:master         // 提交本地test分支作为远程的master分支
$git push origin test:test              // 提交本地test分支作为远程的test分支

git remote add [name] [url]
git remote add 

git push origin

git命令－切换分支
1. 查看远程分支 $ git branch -a 
2. 查看本地分支 $ git branch
3. 切换分支 $ git checkout -b v0.9rc1 origin/v0.9rc1  $ git branch
＃切换回master分支
$ git checkout master

#4.大致流程是：

1、在github上创建项目

2、使用git clone https://github.com/xxxxxxx/xxxxx.git克隆到本地

3、编辑项目

4、git add . （将改动添加到暂存区）

5、git commit -m "提交说明"

6、git push origin master 将本地更改推送到远程master分支。

这样你就完成了向远程仓库的推送。
如果在github的remote上已经有了文件，会出现错误。此时应当先pull一下，即：

git pull origin master
然后再进行：

git push origin master

Project-hosts-download-share

cd /d/git

git clone git@github.com:antknox/Project-hosts-download-share.git.

cd project-hosts-download-share

git add .

git commit -m "2016-10-19"

git push origin master



#5.PS

 git archive master > /d/git/tmp/1.zip
打包



