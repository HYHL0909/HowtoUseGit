假设我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。

git@github.com:HYHL0909/responsive.git

cd responsive

ls 查看有啥

git branch -a 查看本地和远程仓库的 分支

touch test 创建一个文件叫test

git status 查看工作区的状态，位在哪一个分支。修改哪个文件还没有提交

git diff readme.txt //让我看看到底时修改了什么内容

git log 让我们看看我们到底做了啥，展示的是每次的commit 的-m里的内容

git log --pretty=oneline 用于筛选

git reflog 用来记录你的每一次命令。

git add .(文件name)                //添加文件到本地 

git commit -m “first commit”      //添加文件描述信息

git remote -v //查看远程仓库名

git push -u origin main       //把本地仓库的文件推送到远程仓库main                                   分支

但是我们在修改代码时不会直接在main分支上修改，我们先创建一个分支，然后在分支里修改，修改完毕后将该分支与原来的合并，然后删除原来的分支（本地和远程）

git checkout -b dev 创建了分支，并进入分支dev

touch test1.txt //在分支里创建了test1.txt文件

git add .//添加在dev分支

git commit -m 

git push origin dev //推到远程，现在远程和本地都有两个分支 dev和main

git checkout main // 转移到分支main

ls //时刻查看分支下文件的东西。

git merge dev //要合并，先进入main 分支，然后将要合并的写入。

git push origin main //然后将合并的分支main push到远程。

git branch -D dev //删除本地的dev分支，要先进入main分支

git push origin ：dev //删除远程的dev分支。



工作区 你电脑里能看到的目录

![image-20220405202116121](https://raw.githubusercontent.com/HYHL0909/images/main/202204052021333.png)



版本库

工作区有一个隐藏目录`.git`，这个不算工作区，而是Git的版本库。

版本库里很多东西，stage是暂存区。master现在github 默认命名为main

![image-20220405202159984](https://raw.githubusercontent.com/HYHL0909/images/main/202204052022066.png)

git add 把文件添加到暂存区

git commit 提交到当前分支

git checkout --file 可以丢弃工作区的修改。

- 一种是`file`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
- 一种是`file`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

git reset 可以回退版本，也可以从暂存区回退到工作区。

如果放到了版本库也还是可以回退的。但是如果本地版本已经被push到远程库，那就没法修改了。