# git 使用

> ### 基本操作

* 指定用户名和邮箱

  ```shell
  git config --global user.name "dujinwei"
  git config --global user.email "1979159182@qq.com"
  ```

* 指定目录为git可管理的仓库

  ```shell
  git init
  ```

* 添加文件或目录到仓库

  ```shell
   git add STLDataStructure/
  ```

* 提交文件 -m 指定提交说明

  ```
  git commit -m "2021-01-20 第一次上传"
  ```

* 查看工作区状态

  ```shell
  git status
  ```

* 查看修改文件的内容详情

  ```shell
  git diff
  ```

* 查看提交的历史记录

  ```shell
  git log 					#查看详细记录
  git log --pretty=oneline	#查看简单记录  
  ```

* 回退之前的版本 HEAD指向的版本就是当前版本

  ```shell
  git reset --hard HEAD^      #回到上一个版本
  #上上一个版本就是 HEAD^^
  #上一百个版本 HEAD~100
  git reset --hard 566b       #指定commit版本号  回退到指定的版本
  git reflog 					#查看每一次操作命令
  git diff HEAD -- hello.cpp	#查看工作区和版本库里面最新版本的区别
  ```


* 撤销更改

  ```shell
   git checkout -- hello.txt	#撤销本地工作区的更改 不推荐
   git restore hello.txt		#撤销本地工作区的更改 新版本git
   git restore --staged hello.txt #撤销缓冲区的更改 新版本git
  ```

* 删除文件  删除了本地工作区文件

  ```shell
  git rm hello.txt			#从版本库中删除  之后使用commit 提交
  git restore hello.txt		#撤销本地工作区更改
  ```

> ## 远程仓库

* 生成 id_rsa 和 id_rsa.pub 公钥和私钥对文件

  ```shell
   ssh-keygen -t rsa -C "1979159182@qq.com"
  ```

* 添加本地仓库到远程仓库 （首先在github上建一个仓库）

  ```shell
  git remote rm origin					#删除
  git remote add origin git@github.com:jermydu/STLDataStructure.git  #添加
  git push -u origin master								#把内容推送到远程仓库，第一次推送
  git push -f origin master								#推送最新修改-f 强制覆盖
  ```

* 从远程仓库克隆到本地

  ```shell
  git clone git@github.com:jermydu/CppTemplateTutorial.git
  ```

  