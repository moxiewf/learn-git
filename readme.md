0. **工作区**：就是你在电脑里能看到的目录；**版本库**：`git init`命令之后生成的`.git`，git的版本库中存了很多东西，其中最重要的就是成为stage的`暂存区`，还有git自动为我们创建的第一个分支`master`，以及指向master的一个指针`HEAD`
1. 创建一个空目录：learn-Git
2. 把这个目录变成git可以管理的仓库： `git init`
3. 新建文件添加到暂存区：`git add test.txt`
4. 把暂存区的内容提交到当前分支：`git commit -m "add: test.txt`
5. 查看仓库当前的状态：`git status`
6. 查看文件的修改前后对比：`git diff test.txt`
7. 查看从近到远的提交历史：`git log`   `git log --pretty=oneline`；查看每一次的命令历史：`git reflog`
8. 回退到上一个提交版本(git中HEAD表示当前版本)：`git reset --hard HEAD^` (上上个版本 HEAD^^) `git reset --hard commit_id`
9. 查看工作区和版本库里文件最新版本的区别：`git diff HEAD -- test.txt`
10. 丢弃工作区的更改：`git checkout -- text.txt` 意思就是，把test.txt文件在工作区的修改全部撤销，这里有两种情况：①test.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；②test.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。总之，就是让这个文件回到最近一次git commit或git add时的状态。
11. 把暂存区的修改回退到工作区: `git reset HEAD test.txt`
12. 从版本库删除一个文件：`git rm test.txt`
 -----
13. 添加远程仓库：（用本地已有的仓库和远程仓库进行关联，把本地的仓库的内容推送到远程）

    ①在 github新建一个仓库 `learn-git`

    ②将本地已有的仓库与之关联：`git remote add origin git@github.com:moxiewf/learn-git.git
`

    ③把本地仓库的所有内容推送到github的远程仓库上：`git push --set-upstream origin master
`

14. 从远程仓库克隆：（本地没有仓库，直接从github上新建仓库）

     ①登录github新建一个仓库`git-skills`，勾选`Initialize this repository with a README`，这样GitHub会自动为我们创建一个README.md文件。创建完毕后，可以看到README.md文件：

     ②克隆一个本地仓库：`git clone git@github.com:moxiewf/git-skills.git`
     
----