## 本地仓库
### 1.创建文件夹
	cd D:(进入d盘)
	cd mkdir testgit（创建文件夹）
	cd testgit（进入文件夹）
	pwd 显示当前的目录
### 2.通过命令将文件夹变成可以使用git管理的仓库
    1. 在当前文件夹下使用 git init；
    2. 使用命令 git add readme.txt添加到暂存区里面去。
    3. 用命令 git commit -m ‘这是注释’ 告诉Git，把文件提交到仓库
    4. 命令git status来查看是否还有文件未提交
    5. 修改文件内容再次查看文件未提交状态
    6. 使用git diff readme.txt，查看文件修改内容
### 3.版本回退
	1. git log 查看历史记录
	2. git log --pretty=oneline（查看历史记录，精简版）
	3. 版本回退 git reset --hard HEAD^(回退上个版本)
		       git reset --hard HEAD^^(回退上上个版本)
			   git reset --hard HEAD~100（回退到前100个版本）
	4. 通过命令cat readme.txt查看文件内容
	5. 恢复已经回退的版本（通过版本号）
				git reflog获取版本号
				git reset --hard f0142a8恢复指定版本
### 4. 理解工作区与暂存区的区别
	1. 工作区：就是你在电脑上看到的目录，比如目录下testgit里的文件(.git隐藏目录版本库除外)。或者以后需要再新建的目录文件等等都属于工作区范畴。
	2. 版本库(Repository)：工作区有一个隐藏目录.git,这个不属于工作区，这是版本库。其中版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。
	3. 第一步：是使用 git add 把文件添加进去，实际上就是把文件添加到暂存区。
	4. 第二步：使用git commit -m提交更改，实际上就是把暂存区的所有内容提交到当前分支上。
	注：add .所有文件添加到缓存区，commit会提交所有

### 5. Git撤销修改和删除文件操作。
	情景：在我未提交之前，我发现添加5555555555555内容有误，所以我得马上恢复以前的版本，现在我可以有如下几种方法可以做修改：
	1. 如果我知道要删掉那些内容的话，直接手动更改去掉那些需要的文件，然后add添加到暂存区，最后commit掉。
	2. 我可以按以前的方法直接恢复到上一个版本。使用 git reset  --hard HEAD^
	3. 命令 git checkout -- test.txt意思就是，把test.txt文件在工作区做的修改全部撤销
      ①readme.txt自动修改后，还没有放到暂存区，使用 撤销修改就回到和版本库一模一样的状态。
      ②另外一种是readme.txt已经放入暂存区了，接着又作了修改，撤销修改就回到添加暂存区后的状态。


## 远程仓库

先注册github账号，由于你的本地Git仓库和github仓库之间的传输是通过SSH加密的，所以需要一点设置：
### 1. SSH Key设置
	1. 打开 Git Bash窗口工具 



## git在Androidstudio中的使用
	1. 下载安装git客户端
	2. 将git客户端关联到android studio
![](https://i.imgur.com/JKlCX24.png)

    3. 创建本地仓库（一定要选择项目根目录，创建成功之后底部会出现Version Control）

![](https://i.imgur.com/rP7UuTK.png)

	4. 然后将文件添加到版本控制中去，commit提交修改

![](https://i.imgur.com/siuUnBf.png)

	5. 下面就要push到远程仓库了，要注意的是有时候第push会失败，需要pull一下一成push成功

![](https://i.imgur.com/qQAefVU.png)

	6.添加远程仓库地址等同于命令（git remote add origin [远程仓库地址]）

![](https://i.imgur.com/q7DZTIF.png)


![](https://i.imgur.com/p1zSsiD.png)	

	7.查看远程仓库
![](https://i.imgur.com/9CkLQnH.png)