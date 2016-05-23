Git
一 基础学习
	1. git init	初始化
	2. git add <filename> 添加文件到本地仓库  (把文件添加进去，实际上就是把文件修改添加到暂存区)
	3. git commit -m '<DESC>' 将添加好的文件提交到本地仓库 (把暂存区的所有内容提交到当前分支)
	4. git log 查看commit 日志
	5. git log --pretty=oneline 以行的形式显示日子
	6. git rest --hard HEAD^ 回滚到上一个版本
	7. git reset --hard <版本号> 回滚到该版本(可以往前回滚也可以往后回滚)
	8. git reflog 记录每一次命令，查看命令历史，以便确定要回到未来的哪个版本(可以用这个命令早点每次操作的版本号)
	9. git checkout -- <文件名> 文件在工作区的修改全部撤销 (
			一种是 该文件 自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
			一种是 该文件 已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
		)
	10. git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到git checkout命令
	11. git reset HEAD file可以把暂存区的修改撤销掉（unstage），重新放回工作区
	12. git rm <文件名> 用于删除一个文件
	13. git remote add origin git@github.com:michaelliao/learngit.git 关联远程仓库(用ssh公钥的情况)
	14. git push -u origin master 推送数据到远程仓库(第一次推送数据需要加上  -u , master 最新改动需要推送的分支)

二 git的分支应用
	1. git checkout -b dev 创建 dev分支 并切换到该分支 (-b 参数表示创建并切换)
	2. git branch 列出所有分支，当前分支前面会标一个*号
	3. git merge dev 合并指定分支[dev]到当前分支
  	4. git branch -d dev 删除 指定分支[dev]
	5. git checkout master 切换到指定分支[master]
	6. git log --graph 查看到分支合并图	
	7. git log --graph --pretty=oneline --abbrev-commit 看到分支的合并情况	
	8. git merge --no-ff -m "merge with no-ff" dev 强制禁用Fast forward模式合并分支(-m参数，把commit描述写进去)
