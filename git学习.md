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
* ```git reser HEAD <file>``` 你将修改```add``` 进暂存区，这个命令能将暂存区的内容退回工作区
* ```rm file```可以将本地的文件删除，这之后```git status``` 会提示你和版本库中不一致的地方
  * ``` git rm file```  ```git commit -m”“description”``` 可以将版本库中的文件也删除
  * ``` git checkout –file``` 可以将不小心误删的文件从版本库中回复
  * 如果被删除的文件没有commit过，则无法恢复



## 远程仓库 Github