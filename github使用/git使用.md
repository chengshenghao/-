# 创建数据库
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
	1. 如果我知道要删掉那些内容的话，直接手动更改去掉那些需要的文件，然后add添加到暂存区，最后commit掉。
	2. 我可以按以前的方法直接恢复到上一个版本。使用 git reset  --hard HEAD^
	


	