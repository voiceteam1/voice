#配置用户名和邮箱
1  git help git   ---查看帮助文档
    2  git config --global user.name "leorunwind"
    3  git config --global user.email "luorunwen@163.com"
   
#本地库创建
   4  cd {path}/leosite-code/  ---进入到要push到远程库的文件夹，{path}替换为具体的project目录
   5  git init   ---在当前文件夹创建一个空的git本地库
   6  git add -all   ---将当前目录下的所有文件都添加到git本地库里
   7  git commit -m 'first commit'   ---提交并加上提交信息
   
#连接远程库并提交
   8  git remote add origin https://github.com/leorunwind/leosite.git   ---连接远程库，回车会让你输入用户名和密码
   9  git push -u origin master
   10  git pull -u origin master   ---如果上一条push提示failed to ...，用pull回拉从而同步版本
   11  git push -u origin master   ---push到远程库



1 Linux下Git和GitHub环境的搭建

第一步： 安装Git，使用命令 “sudo apt-get install git”

第二步： 创建GitHub帐号

第三步： 生成ssh key，使用命令 “ssh-keygen -t rsa -C "your_email@youremail.com"”，your_email是你的email

第四步： 回到github，进入Account Settings，左边选择SSH Keys，Add SSH Key,title随便填，粘贴key。

第五步： 测试ssh key是否成功，使用命令“ssh -T git@github.com”，如果出现You’ve successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。

第六步： 配置Git的配置文件，username和email

git config --global user.name "your name" //配置用户名

git config --global user.email "your email" //配置email

 

2 利用Git从本地上传到GitHub

第一步： 进入要所要上传文件的目录输入命令 “git init”

第二步： 创建一个本地仓库origin，使用命令 “git remote add origin git@github.com:yourName/yourRepo.git”
youname是你的GitHub的用户名，yourRepo是你要上传到GitHub的仓库

第三步： 比如你要添加一个文件xxx到本地仓库，使用命令 “git add xxx”，可以使用“git add .”自动判断添加哪些文件

然后把这个添加提交到本地的仓库，使用命令 ”git commit -m ”说明这次的提交“ “

最后把本地仓库origin提交到远程的GitHub仓库，使用命令 ”git push origin master“

 

3 从GitHub克隆项目到本地

第一步： 到GitHub的某个仓库，然后复制右边的有个“HTTPS clone url”

第二步： 回到要存放的目录下，使用命令 "git clone https://github.com/chenguolin/scrapy.git"，红色的url只是一个例子

第三步： 如果本地的版本不是最新的，可以使用命令 “git fetch origin”，origin是本地仓库

第四步： 把更新的内容合并到本地分支，可以使用命令 “git merge origin/master”

 

如果你不想手动去合并，那么你可以使用： git pull <本地仓库> master // 这个命令可以拉去最新版本并自动合并

 

4 GitHub的分支管理

创建

1 创建一个本地分支： git branch <新分支名字>

2 将本地分支同步到GitHub上面： git push <本地仓库名> <新分支名>

3 切换到新建立的分支： git checkout <新分支名>

4 为你的分支加入一个新的远程端： git remote add <远程端名字> <地址>

5 查看当前仓库有几个分支: git branch

删除

1 从本地删除一个分支： git branch -d <分支名称>

2 同步到GitHub上面删除这个分支： git push <本地仓库名> :<GitHub端分支>

 

5 常见错误

1 如果出现报错为ERROR: Repository not found.fatal: The remote end hung up unexpectedly则代表你的 origin 的url 链接有误，可能是创建错误，也可能是这个 git@github.com:xxx/new-project.git url 指定不正确。重新创建。
--------------------- 
作者：lovewingss 
来源：CSDN 
原文：https://blog.csdn.net/lovewingss/article/details/50943843 
