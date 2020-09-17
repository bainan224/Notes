### git

##### terminal指令：

* 启动：git --version

* github: git config --global user.name "bainan224"

  ​              git config --global user.email "                  "

### key

* Git Bash Here 
* git ssh-keygen -t rsa -C "email"
* 主目录：.ssh 打开id_rsa.pub (Notepad++) 

#### Github

* settings -- SHH and GPG keys -- New SSH key 复制粘贴id_rsa.pub内容

### Github Repository

* New repository -- name -- Public -- Create 

### Git Bash Here

* 进入本地目录打开 Git Bash Here 
* git init 初始化一个目录（隐藏目录.git）
* 创建一个文件 biji.md
* 将文件加入仓库暂存区：git add .(添加所有目录)   git add biji.md (添加具体目录)

* 将文件提交到仓库：git commit -m "biji.md(描述文件)"

* 查看仓库状态：git status

* 日志：git log
* github：git remote add origin git@github.com:bainan/Notes.git
* 远程推送：git push -u origin master

### Idea

* 创建project -- setting Version Control Git(test) Github(username password)
* get add . 添加所有文件
* 警告解决：git config core.autocrlf true --git add .
* 第一次提交：git commit -m “first commit”
* github：git remote add origin git@github.com:bainan/quickstart.git
* 远程推送：git push -u origin master
* idea中修改：git commit -m "update"
* 远程github修改：本地git pull

