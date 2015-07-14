# **Github的学习使用之旅** #


##Git和其他版本控制系统的主要差别  ##
	1. Git 只关心文件数据的整体是否发生变化，而大多数其他系统则只关心文件内容的具体差异。
	2. Git 并不保存这些前后变化的差异数据。实际上，Git 更像是把变化的文件作快照后，记录在一个微型的文件系统中。每次提交更新时，它会纵览一遍所有文件的指纹信息并对文件作一快照，然后保存一个指向这次快照的索引。为提高性能，若文件没有变化，Git 不会再次保存，而只对上次保存的快照作一链接。  
	我们可以从文件所处的位置来判断状态：
		- 如果是 Git 目录中保存着的特定版本文件，就属于已提交状态；
		- 如果作了修改并已放入暂存区域，就属于已暂存状态；
		- 如果自上次取出后，作了修改但还没有放到暂存区域，就是已修改状态。
## .gitignore文件 ##
	- 所有空行或者以注释符号 ＃ 开头的行都会被 Git 忽略
	- 可以使用标准的 glob 模式匹配
	- 匹配模式最后跟反斜杠（/）说明要忽略的是目录
	- 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号（!）取反
## GIT常用命令 ##
	- git init 对现有的某个项目开始用 Git 管理。初始化后，在当前目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中
	- git add 将文件纳入版本控制（跟踪）。git add . 全部添加
	- git clone [url] 从现有仓库克隆
	- git diff 查看暂存文件更新了哪些部分
	- git diff --cached 查看暂存文件和上次提交之间的差异
	- git commit 提交以暂存的文件到本地仓库
	- git commit -v 将修改差异的每一行都包含到注释中来 
	- git commit -m 后年直接跟上提交说明
	- git commit -a 自动把所有已经跟踪过的文件暂存起来一并提交，跳过git add步骤
	- git commit --amend 修改最后一次提交
	- git reset HEAD filename 取消已经暂存的文件
	- git checkout – filename 取消对文件的修改
	- git rm 将文件从工作目录中删除
	- git rm --cached 跟上文件或目录名称（支持正则）将文件从git仓库中删除，但仍保留在当前工作目录中
	- git mv file_from file_to 改名
	- git remote查看当前配置有哪些远程仓库 –v(verbose)
	- git remote add [remote-name] [url（SSH/HTTPS/SUBVERSION）] 关联本地仓库到远程
	- git push [remote-name] [branch-name(master is default)] –f(forcefully) 提交本地更新到远程
	- git fetch [remote-name] 从远程抓取数据
	- git remote show [remote-name] 查看远程仓库信息
	- git remote rename [old name] [new name] 重命名远程仓库
	- git remote rm [remote-name] 断开连接（我的理解）
	- git tag 标签操作
	- git log 查看日志 （q退出）
		- -p  按补丁格式显示每个更新之间的差异。
		- --word-diff 按 word diff 格式显示差异。
		- --stat  显示每次更新的文件修改统计信息。
		- --shortstat 只显示 --stat 中最后的行数修改添加移除统计。
		- --name-only 仅在提交信息后显示已修改的文件清单。
		- --name-status   显示新增、修改、删除的文件清单。
		- --abbrev-commit 仅显示 SHA-1 的前几个字符，而非所有的 40 个字符。
		- --relative-date 使用较短的相对时间显示（比如，“2 weeks ago”）。
		- --graph 显示 ASCII 图形表示的分支合并历史。
		- --pretty    使用其他格式显示历史提交信息。可用的选项包括 oneline，short，full，fuller 和 format（后跟指定格式）。
		- --oneline   `--pretty=oneline --abbrev-commit` 的简化用法。
		- -(n)    仅显示最近的 n 条提交
		- --since, --after    仅显示指定时间之后的提交。
		- --until, --before   仅显示指定时间之前的提交。
		- --author    仅显示指定作者相关的提交。
		- --committer 仅显示指定提交者相关的提交。


参考资料：  
markdown格式简介及使用：[http://wowubuntu.com/markdown/index.html](http://wowubuntu.com/markdown/index.html "http://wowubuntu.com/markdown/index.html")  

