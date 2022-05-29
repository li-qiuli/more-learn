https://ohshitgit.com/ 

 

1. 下载git 
Git安装地址：https://git-scm.com/download/mac  
2. pkg包下载完成，双击安装 
3. 打开终端 

git version命令查看安装版本（出现git version 2.20.1安装成功） 

4. cd ～/.ssh  查看 .ssh 
-bash: cd: ～/.ssh: No such file or directory 

如果你的结果出现上面代码，说明.ssh文件夹不存在，执行下方 

==》ssh-keygen -t rsa -C xxxx@xxx.com （Github注册账号） 

=>接下来 默认直接按 回车 就可以了 

5. 密钥设置 
settings --> SSH and GPG keys --> Title表单：输入github注册账号 -->key：输入～/.ssh/id_rsa.pub文件里的内容 

<通过cat 命令查看 id_rsa.pub 里面的key  ： cat ~/.ssh/id_rsa.pub > 

7. 创建项目 
返回到主页，www.github.com 

Start a project -> 进入到了 “Create a New Repository”页面 -> Create repository 

 

8. 本地仓库的创建及代码上传（Git） 

打开终端，输入以下命令： 

touch README.md                   //新建一个README文档，若上一步勾选了创建 

README.md                              //提交时导致冲突   

git init                                        //初始化本地仓库   

git add README.md                  //添加刚刚创建的README文档   

git commit -m "你的注释...."       //提交到本地仓库，并写一些注释   

<==>git cz(安装cz)   

git remote add origin https://github.com/imthinktwice/TestRepository.git   

//连接远程仓库并建了一个名为origin的别名，也可以为其他名字，youname记得替换成你的用户名   

git push -u origin master                               

//将本地仓库的文件提交到别名为origin的地址的master下， 

//-u为第一次提交，需要创建master分支，下次就不需要了  

 

9. git指令 

 

## 查看 

 

本地查看(工作区-----暂存区 ) 

tldr git 

tig --all 

 

git status     查看状态 

 

查看差异 

git diff                              暂存区-----工作区             
git diff --cached <file>              暂存区-----上一个commit   
git diff HEAD                         工作区-----当前分支最新commit 
git diff <first-branch>···<second-branch> 两次提交之间 
git diff --shortstat "@{0 day ago}"       显示今天你写了多少行代码 

 

git show <commit>             显示某次提交的        元数据和内容变化 
git show --name-only <commit> 显示某次提交发生    变化的文件 

 

git reflog                    当前分支    最近几次提交 

 

（操作）查看远程仓库 

git remote                 查看仓库的命名 

git remote -v              显示所有远程仓库 

git remote show <origin>  显示某个远程仓库信息 (eg:pull与push时合并的本地分支与远程分支名) 

 

 

## 发布流程 

 

git init                      初始化本地版本库 
git init <project-name>       初始化Git库，并新建一个目录 

 

git add < .| files-names >    跟踪文件（工作区 ----> 暂存区） 

（撤销）====》 

git checkout <file>               (指定文件)暂存区    ----> 工作区                
git checkout .                        (所有文件)暂存区.   ----->工作区 

（查看）====》 

git ls-files -s                          查看（git add操作后） 

 

 

git commit -m <messages>                提交文件（git cz）（到分支） 

git commit [file1][file2] -m <message> （指定文件）暂存区---->仓库区 

（撤销）====》 

git checkout <commit> <file>      (指定文件)commit ----> 暂存区和工作区 

git commot --amend                      更改之前一次commit的描述信息 

（查看）====》 

git log                                              查看提交版本历史 （git commit命令后） 

git log --stat                                    显示commit历史，及每次commit发生变更的文件 

 

 

git remote add <origin> <url>      增加一个新的远程仓库，并命名  

（修改）====》 

git remte origin set-url URL            修改远程 URL 

 

git fetch <origin>                 下载远程仓库的所有变动 

git fetch --all 
 

 

git pull <origin> <master>         下载代码及快速合并 

 

git push <origin> master           上传代码及快速合并(到远程)  
git push <origin> --force          强行推送当前分支到远程仓库，即使有冲突 

git push <origin> --all            推送所有分支到远程仓库 

git push origin dbg_star:dbg_star  新建的本地分支push到远程服务器，远程分支与本地分支同名（当然可以随意起名） 

 

## 分支 

### 本地分支 

git branch                    显示所有分支  

git branch <new-branch>       创建新分支  

git branch -d <branch>        删除本地分支  

 

git checkout <existed-branch> 切换到指定分支 

git checkout -                切换到上一分支 

git checkout -b <new-branch> <based-branch> 新建一个分支，并切换到该分支 
             

git merge [--no-ff] <from-branch>  和并分支到当前分支 

 

get reset [--hard] <existed-branch> 

 

 

### 远程分支 

git branch -r                列出所有远程分支 

 

git push origin --delete <branch-name> 删除远程分支 
git branch -dr <remote/branch>         删除远程分支 

 

 

### 本地加远程分支 

git branch -a               列出所有本地+远程分支 

 

### 本地与远程建立关系 

git branch --track <branch> <remote-branch> 新建一个分支---指定的远程分支  建立追踪关系 
git branch --set-upstream <branch> <remote-branch>现有分支---指定的远程分支之间   建立追踪关系 

 

### 删除与修改待验证 

git rm <file>               删除 工作区文件与暂存区文件 

git rm --cached <file>      停止跟踪文件，但文件会保留在工作区 

git mv <old-filename> <new-filename> 修改 工作区与暂存区文件名 

 

# 本地 

git clean -n                                    查看将被清理的新增文件 

git clean -f                                     清理新增的文件（没有执行git add的文件都将被清理 ） 

 

git stash                      把所有未commit的修改，都扔进暂存区（git pop命令找回来） 

git stash list                 查看 

git stash drop                 永久删除（暂存区里内容） 

 

git reset（--soft、--mixed、--hard） 

git reset --hard               重置暂存区与工作区（上一次commit保持一致）      

 

git reflog show                查看操作日志 

git reflog show [dev|master|分支名] 

 

git reset --hard  dev@{0}      回到想回到的位置（如： dev@{1}） 

git reset <file>               重置暂存区的指定文件（上一次commit保持一致，工作区不变） 

git reset <commit>             重置暂存区为指定commit（工作区不变） 

git reset --hard <commit> 重置暂存区和工作区为指定commit（当前分支的HEAD为指定commit） 

git reset --keep [commit]      重置当前HEAD为指定commit（暂存区和工作区不变，暂时将未提交的变化移除，稍后再移入） 

git reset --soft HEAD~1        把最近一次git commit提交的内容，撤回到未执行前的状态 

 

 

注意: 

1.<commit>被push到公共仓库后，再使用git reset <commit>时应当注意，或永远不应该使用它。因为，使用git reset会删除其他团队成员的提交，会给团体协作带来问题。项目记录看起来像突然丢失了一大块。 

2.git reset --hard 上一次commit保持一致，需对文件做了提交，如果未提交，git reset --hard 将导致无法恢复 

 

 

  

 

10. git配置文件 .gitconfig 

git config --list                 显示当前的Git配置 

 

git config -e <--global>          编辑Git配置文件 

设置提交代码时的用户信息 

git config [--global] user.name "[name]" 
git config [--global] user.email "[email address]" 

 

 

 

取消跟踪全部文件 

 

 

 

git remote set-url 

 

 

 

# 创建分支规范 

 

master ：主分支           可用的、稳定的、可直接发布的版本，不能直接在该分支上开发 

1. 修补bug（fixbug）分支    从Master分支上面分出来 

采用fixbug-*的形式 

创建一个修补bug分支： 

git checkout -b fixbug-0.1 master 

修补结束后，合并到master分支： 

git checkout master 

git merge --no-ff fixbug-0.1 

git tag -a 0.1.1 

再合并到develop分支： 

git checkout develop 

git merge --no-ff fixbug-0.1 

删除"修补bug分支"： 

git branch -d fixbug-0.1 

develop : 开发主分支    代码是最新，新功能开发，只合并操作，不能直接在该分支上开发 

2. 功能（feature）分支  开发某种特定功能 

可以采用feature-*的形式命名。 

创建一个功能分支： 

git checkout -b feature-x develop 

开发完成后，将功能分支合并到develop分支： 

git checkout develop 

git merge --no-ff feature-x 

删除feature分支： 

git branch -d feature-x 

 

 

3. 预发布（release）分支   合并到Master分支之前,预发布的版本进行测试。 

创建一个预发布分支： 

git checkout -b release-1.2 develop 

确认没有问题后，合并到master分支： 

git checkout master 

git merge --no-ff release-1.2 

 对合并生成的新节点，做一个标签 

git tag -a 1.2 

再合并到develop分支： 

git checkout develop 

git merge --no-ff release-1.2 

最后，删除预发布分支： 

git branch -d release-1.2 

 

注意事项： 

一个分支尽量开发一个功能模块. 

feature 分支在申请合并之前，最好是先 pull 一下 develop 主分支下来，看一下有没有冲突，如果有就先解决冲突后再申请合并。 

 