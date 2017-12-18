
## 解决git 无法运行的问题
1. 进入Git安装目录
1. 如C:\Program Files\Git\usr\bin
1. 将 msys-2.0.dll拷贝到上一级目录，
1. 然后在原来的usr\bin目录下执行下面命令
1. rebase -b 0x76000000 ..\msys-2.0.dll
1. rebase -b 0x30000000 ..\msys-2.0.dll
1. 然后再拷贝回去替换这个DLL文件

## 本地git的使用
* git config --global user.name "姓名"
* git config --global user.emall "邮箱"
* git initi 初始化git仓库
* git add "文件名" 添加文件到暂存区
* git commit -m "修改日志"
* git status 查看文件变动
* git diff 查看文件修改内容
* git log --pretty=oneline查看历史版本
* git reflog 查看历史操作记录
* git reset --hard HADE 回退到上一个版本
* git reset --hard 版本号  回退到指定版本
* git checkout -- "文件名" 撤销工作区修改的内容
* git reset HADE "文件名" 将暂存区修改回退到工作区
* ssh-keygen -t rsa -C "邮箱" 生成密钥  在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人
* git clone 远程仓库地址  拷贝远程仓库代码 
* 查看分支：git branch
* 创建分支：git branch <name>
* 切换分支：git checkout <name>
* 创建+切换分支：git checkout -b <name>
* 合并某分支到当前分支：git merge <name>
* 删除分支：git branch -d <name>

## Git远程分支管理

* git checkout -b 本地分支名x origin/远程分支名x
* git pull # 抓取远程仓库所有分支更新并合并到本地
* git pull --no-ff # 抓取远程仓库所有分支更新并合并到本地，不要快进合并
* git fetch origin # 抓取远程仓库更新
* git merge origin/master # 将远程主分支合并到本地当前分支
* git co --track origin/branch # 跟踪某个远程分支创建相应的本地分支
* git co -b <local_branch> origin/<remote_branch> # 基于远程分支创建本地分支，功能同上
* git push # push所有分支
* git push origin master # 将本地主分支推到远程主分支
* git push -u origin master # 将本地主分支推到远程(如无远程主分支则创建，用于初始化远程仓库)
* git push origin <local_branch> # 创建远程分支， origin是远程仓库名
* git push origin <local_branch>:<remote_branch> # 创建远程分支
* git push origin :<remote_branch> #先删除本地分支(git br -d <branch>)，然后再push删除远程分支
