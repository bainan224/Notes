## git多人协作

##### 项目初始化阶段

* 打开主目录（study）,打开Git Bash Here

* （Git中创建）command-parctice

  git init command-practicecd command-practice(进入此分支)

* cd  command-practice  (进入此分支)

* 添加内容（biji.md）

* (不需要往远程推的文件)  .gitignore   HELP.md  target(文件夹)-system.dll

* .gitignore(notepad++)--(target/   HELP.md)

* git add .

* git commit -m"***"

* git status

* 创建一个仓库（github）[command-practice]

* git status

* git remote add origin git@github.com:bainan224/command-practice.git

* git push -u origin master

## 协作者添加

##### 克隆编辑

* git clone  地址     [ 项目地址复制 (Shift+insert) ]
* 创建bainan.md并编辑
* git add .
* git status
* git commit -m "**"
* git  status
* git push origin master
* [当远程版本新] git pull  退出键   ：wq
* git push origin master

### 多人编辑一行数据

* 编辑数据
* git add. 等
* git pull 下拉  git push -u origin master
* 打开文件，手动删除 ，再一次上传

### 多分支协作

* git branch 查看分支
* git branch dev 添加dev分支
* git checkout dev  退出当前分支，进入dev分支
* 创建soft文件夹  添加图片
* git add .等

## 协作者在dev分支上编辑

* git pull
* 进入dev分支
* 查看分支
* git add .等
* git push origin dev
* 如有人操作  git pull

### 分支合并

* 切换分支到master
* git merge dev  (合并)
* git add . 等

### 本地和远程分支删除

* git branch -d dev(删除本地分支)
* git branch -r -d origin/dev(删除远程分支)
* git add .  等
* git push origin:dev
