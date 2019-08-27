git使用:
创建库
1.在某盘目录下面创建文件夹，例如 D:\git
2.打开 git bash ，用于命令符操作
3.$ cd /d/git  回车
4.$ git init

创建文件 并添加到库(切忌使用记事本编辑)
1.$ git add 文件名（包括扩展名，多个文件的话一次添加）
2.$ git commit -m ""     -m以及之后的内容不是必输项。是对提交的代码文件的一种说明

各种命令操作符
$ git status  查看库状态 提交状况
$ git diff 或者 $ git diff 具体文件名（readme.txt）查看文件提交修改状态况 与本地对比
$ git log 查看代码提交记录
$ git relog 查看命令历史

修改文件后也要使用 增加和提交命令

回退和恢复版本
$ git reset --hard HEAD^  回到上一个版本，本地代码直接变回
$ git reset --hard HEAD^^  回到上上个版本
$ git reset --hard HEAD~100  回到往前100个版本
$ git reset --hard 3628164  直接使用版本号回退，更准确，只写前几位就可以，git会搜索
原理：Git在内部有个指向当前版本的HEAD指针，回退只是将指针指向了指定版本，并且更新了工作区的文件。

git add命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执行git commit就可以一次性把暂存区的所有修改提交，指针同时指向最新。
所以 如果修改了文件，只add 不commit文件并不会被提交

这里的工作区就是指本地文件，暂存区是git服务器的暂时存储地。

撤销修改
git checkout -- readme.txt
撤销修改就是撤销本地文件的修改。这里的撤销有两种：
1.暂存区没有add文件，恢复到已经提交的最新版本。
2.暂存区已经add文件，恢复到暂存区提交的 文件。

删除文件
$ git rm readme.txt

远程库
由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息
1.$ ssh-keygen -t rsa -C "youremail@example.com"
2.默认回车
3.在C盘找到 .ssh文件夹，打开 id_rsa.pub，复制文件内容
4.在 github打开个人账户，找到setting，左侧目录打开 SSH and GPG keys
5. 点击 New SSH key 
6.起名字，在key中粘贴之前复制内容， Add SSH key 
7. $ ssh -T git@github.com 验证是否成功

将本地库关联至github远程库
$ git remote add origin git@github.com:gh-hao/hao-gitytest.git
$ git push -u origin master


xxxxxxx

