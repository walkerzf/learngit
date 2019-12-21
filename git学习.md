# Git

* Git is a software to control version，and is a free software.

## 安装Git

* 在官网下载windows版本的git

* 利用GItBash​在你想建立版本库的地方建立版本库
  

## 创建本地版本库

  * ```mkdir```  （the content of your respositories）或者你在本地新建一个文件夹，利用cd 命令到这个地方，默认的路径是```c/user```，其他的路径需要```cd  /路径```
  * ```cd``` （目录下）
  * ```git init`` （初始化） 
      * 这个目录里面的文件就可以利用Git来进行管理了
  * ```pwd```命令可以显示当前目录
* 在``` git init``` 初始化之后，将文件添加到版本库，有两个步骤
  * ```git add <file>```
  * ```git commit -m “ description”```   这里的```commit```将```add```的文件都添加进版本库



## 版本回退

* ```git status```命令可以随时掌握工作区的状态
* ```git diff```可以查看修改的内容
* ```HEAD``` 指向当前版本 
* ```git  reset --hard commit_id```可以在任意的```commit```版本中穿梭
* ```git log ```可以查看提交历史 ```–-pretty=oneline```可以使查看历史变的简洁    
  * 碰到无法退出的情况，利用```Q```

* ```git reflog```查看命令历史，以便要回到哪个版本…
## 工作区（Working Directoy）和暂存区（stage）

* ```git add ``` 命令就是将工作区的内容存到暂存区
* ```git commit``` 上次之前 ```add``` 到 ```stage``` 的内容添加进版本库 ```Repository```
  * ```Repository``` 是目录下的一个隐藏的文件夹
* ```git checkout -–file ```   当你还没有将修改 ```add``` 进暂存区，想丢弃 工作区的内容
* ```git reset HEAD <file>``` 你将修改```add``` 进暂存区，这个命令能将暂存区的内容退回工作区
* ```rm file```可以将本地的文件删除，这之后```git status``` 会提示你和版本库中不一致的地方
  * ``` git rm file```  ```git commit -m”“description”``` 可以将版本库中的文件也删除
  * ``` git checkout –file``` 可以将不小心误删的文件从版本库中回复
  * 如果被删除的文件没有commit过，则无法恢复



## 远程仓库 Github

* 注册一个Github账号
* 传输利用SSH加密，所以对传输进行设置
  1. ```ssh-keygan -t  rsa -C”youremail@mail.com“”``` 创建SSH KEY
  2. 可以在```/user/15524/```目录下找到```.ssh``` 目录，里面有```id_rsa``` 和 ```id_rsa.pub```文件，这两个就是SSH 的密钥对，前者是秘钥，后者是公钥
  3. 公钥需要输入在Github的Account Settings中的SSH Keys页面
* 建立一个新的版本库  ```Repository``` ，这个仓库可以有两种方式
  * 从别的库导入
  * 从本地已经存在的Repository中push
    * ```git remote add origin htttps://github.com/walkerzf/Respository.name.git```
    * ``git push  -u origin master``
    * ```-u``` Git不但会把本地的```master``` 分支内容推送的远程新的```master```分支，还会把本地的```master```和远程```master``` 关联起来
    * 之后只需利用 ``` git push origin master```
  * 重新创建新的库
* ``` git clone <>``` 克隆远程的库到本地



## 分支管理

* ```git branch``` 查看分支
* ```git branch <name>``` 创建分支
* ```git checkout <name >``` ```git switch <name>``` 切换分支
* ```git checkout -b <name>```  ```git switch -c <name>``` 创建和切换分支
* ```git merge <name>``` 合并某分支到当前分支
* ``` git branch -d <name>``` 删除分支



## 解决冲突

* 在分支中先于master ```commit``` ，在master提交的时候就会产生```confliction``` ，```fixed```之后才可以提交
* ```git merge 分支名```
* ```git log –graph``` 可以看到分支合并图
* ``` git merge –no-ff -m”“description ” 分支名 ``` 这样禁用``` Fast foward```，利用普通模式合并，合并后的历史有分支，能看出做过合并，而```Fast forword``` 合并看不出来曾经做过合并



## Bug 分支

* ``` git stash``` 保留现场工作，再去master上修复bug，再``` git stash pop ``` 回到工作现场
* ``` git cherry-pick<commit>``` 命令，将bug提交的修改“复制”到当前分支，避免重复劳动 
* ```git stash list``` 保留现场的列表



## Feature 分支

* 开发一个新feature ，最好新建一个分支；
* 如果要丢弃一个没有被合并过的分支， ``` git branch -D<name>``` 强行删除



## 查看远程库信息

* 查看远程库信息 ，使用 ``` git remote -v```
* 本地新建的分支如果不推送到远程，对其他人就是不可见的
* 从本地推送分支，使用 ```git push origin branch-name``` 如果推送失败，先用 ```git pull```抓取远程的新提交
* 在本地创建和远程分支对应的分支，使用``` git checkout -b branch-name origin/brance-name``` 。本地和远程分支的名称最好一致
* 建立本地分支和远程分支的**关联**，使用``` git branch –set-upstream branch-name origin/branch-name```
* 从远程抓取分支，使用```git pull```，如果有冲突，要先处理冲突