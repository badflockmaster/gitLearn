# git 命令学习笔记
## git 初始化配置
1. git config --global user.name "在这里输入username"
2. git config --global user.mail "在这里输入usermail"

ps: 注意命令中的空格，输入之后， enter键执行

## 创建本地版本库
1. 首先需要创建一个文件夹（例如我想在d:/github/GitLearn中创建一个版本库）
2. cd d:/github/gitLearn
3. pwd
4. 执行上述命令创建相应的文件夹
5. 其中的cd 用于创建一个文件夹
6. 而pwd 用于显/示当前路径
7. 正确执行gitBash 应该显示 /e/github/gitLearn
8. 此时表示git正确执行了我们的命令，创建了相应的文件夹

### 本地版本库的创建
```git
$ git init
Initialized empty Git repository in D:/github/gitLearn/.git/
```
运行git init 命令

正确运行后，显示上述结果

PS：此时我们查看我们创建的文件夹，会发现在我们创建的文件中多了一个.git 文件夹。如果没有发现，那么这个文件可能被隐藏。
```
ls -ah
```
运行这一条命令即可显示隐藏的.git文件夹
此时本地版本库已经创建完成。

## 使用git
### 创建一个文本文件，在这里我创建一个GitBaseCommand.md，用来记录git的学习笔记
PS：一定要放在GitLearn目录下，可以放在子目录下。
git add 用于将文件添加git中去。
```
git add gitBaseCommand.md
```
当然，此时不会显示任何东西。
接着输入git commit。告诉git，把文件提交到仓库。
```
git commit -m "message"
```
必须要在commit命令后面增加一个参数，并且输入提示消息。
以避免出现不必要的麻烦。
### 查看status
现在我们已将gitBaseCommand.md 文件添加并且提交到git中去了。可以，开始继续工作，修改文件了。

现在修改文件。修改完成后，输入git status
```
git status
```
git status命令，可以查看当前git的状态。
![status](assets/markdown-img-paste-20171002213733855.png)
显示，在master分支上，文件被修改，但是却没有add和commit。
```
git add gitBaseCommand.md
```
等一下才commit文件
现在我们先查看一下文件状态
```
git status
```

![addstatus](assets/markdown-img-paste-20171002214808421.png)
显示信息提示我们。文件已经被添加到git。可以commit。
```
git commit -m "meassage"
```
提交完成。既然我们学习了git  status命令。
那么我们来查看一下commit后的git status
```
git status
```
![commit](assets/markdown-img-paste-20171002215349216.png)
信息显示，现在没有文件要commit。
### 版本倒退
我们现在已经提交过两次了。如果我们想回到上一次提交的时候应该怎么做呢？
或许我们应该查看一下，之前我们提交的信息。 以免回到错误的版本。
```
git log
```
![log](assets/markdown-img-paste-20171002220147407.png)

git log命令可以查看最近到最远的log。即我们提交的日志。
如果觉得显示的信息太复杂，添加 --pretty=oneline 参数。
```
git log --pretty=oneline
```
![oneline](assets/markdown-img-paste-20171002220358555.png)
从显示的信息可以，看出，我们一共提交了两次。那些数字，是commit的id。用这个id我们可以回到我们想要去的版本。
```
git reset --hard b33a95
```
ID可以不用写完，git会自动去查找的。
