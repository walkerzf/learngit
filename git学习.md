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