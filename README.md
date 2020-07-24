
##### 全局配置
```
git config --global user.name "CoronetLiu"
git config --global user.email "865753224@qq.com"
```

##### 初始化仓库
```
@本地初始化新仓库
git init

@克隆远程仓库至本地
git clone https://github.com/CoronetLiu/Test.git
```

##### 提交
```
git add README.txt  //提交某文件
git add .   //提交新的和修改过的文件,不包括删除信息
git add -u  //提交修改和删除信息,不提交新的文件
git add -A  //提交全部
git commit -m '注释'   //提交必带注释
git commit -am '注释'  //用于提交已跟踪过的文件(可省略git add操作)
```

##### 版本
```
git log     //查看commit记录
git status  //查看仓库状态
git reflog  //查看全部版本
git reset --hard HEAD^  //回退到最新版本(修改的代码不存在)
git reset --hard XXXX   //回退到某一版本
git reset --soft HEAD^  //回退到上次commit状态(修改的代码存在暂存区)
git push -f //强推到远程
git stash   //保存本地修改文件至暂存区(回退至上次commit状态)
git stash list  //查看暂存区存储列表
git stash apply@{num}   //应用某个存储但不会从存储列表中删除
git stash drop@{num}    //从存储列表中删除某个存储
git stash pop   //取出暂存区存储列表至工作区并删除相应存储(默认第一个)
git stash pop stash@{num}   //取出某个暂存区文件至工作区并删除相应存储
```

##### 分支
```
git branch      //查看本地分支
git branch -a   //查看本地和远程分支
git branch -r   //查看远程分支
git branch <name>     //创建分支
git checkout <name>   //切换分支
git checkout -b <name>  //创建切换分支
git branch -m <name>    //修改分支名称
git branch -d <name>    //修改分支名称
git fetch   //更新远程分支列表
git branch -d <name>  //删除本地分支(若该分支未合并至上游分支,则不会执行删除操作)
git branch -D <name>  //强制删除本地分支
git push origin --delete <name>   //删除远程分支
git push origin :<name>   //删除远程分支
```

##### 推送
```
@首次推送
git remote add origin https://github.com/CoronetLiu/Test.git
git push -u origin master

@后续推送
git pull origin master  //本地同步
git push origin master  //推送远程

```

##### 重置仓库(删除所有历史提交记录,使之成为拥有最新版本的新仓库)
```
git checkout --orphan <name>  //基于当前分支建立独立的分支
git add -A
git commit -am '注释'
git branch -D master
git branch -m master
git push -f origin master
```

