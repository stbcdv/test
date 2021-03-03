# git 使用

### 安装/查看版本信息/指向

```git
brew install git
git --version

brew link git --overwrite
brew unlink &&  brew link git
```

### 权限设置

```git
git config --global user.name "用户名"
git config --global user.email "邮箱地址"
```

#### [权限相关操作](https://blog.csdn.net/themagickeyjianan/article/details/79683980)

```git
# 查看配置信息
git config --list
# 修改config
git config --global --add configName configValue
git config --global --unset configName
git config --global configName configValue
git config --global configName
```

### 建立仓库

 <kbd>git clone</kbd>同 <kbd>git init</kbd> 一样的作用,也是创建本地仓库,只不过  <kbd>git init</kbd>是直接将本地项目作为本地仓库,而<kbd>git clone</kbd> 是将远程项目克隆到本地并作为本地仓库.

如果是使用 `git init` 命令初始化的本地项目,可能没有远程仓库,自然也就不需要推送.如果后来创建了远程仓库,那么你自然是想要将本地仓库推送到远程仓库的,因此你需要准确告诉 `git` 你要推送到哪个远程仓库.
使用 `git remote add origin git@github.com:username/repos.git` 命令添加远程仓库信息,这样就建立了本地仓库和远程仓库的关联,以后就可以正常推送到远程仓库了

```
git clone <仓库地址> <本地目录>

建立文件夹
git init # 建立本地仓库
```

### 提交文件

```
# 文件已修改
git add <文件名> # 提交到暂存区
git status # 查看文件状态
git commit -m '备注修改的内容简介(可中文)'
git status
## 以上相当于对本地仓库操作(不会传到github中)
git push # 提交修改到远端仓库(提交到GitHub仓库中)

## 命令合并
git commit -m 'message' && git push

# 取消暂存
git restore --staged <文件>..
```

#### 文件提交再修改

```
git commit --amend //追加提交，它可以在不增加一个新的commit-id的情况下将新修改的代码追加到前一次的commit-id中
```



#### 其他文件操作

```
# 撤销 add
git reset .

# 丢弃工作区中的修改
#一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
#一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
#总之，就是让这个文件回到最近一次git commit或git add时的状态。
git checkout -- filename

# 删除文件
rm <文件名>
git rm <文件名>
git commit -m 'delete'
```



### 生成密钥

```
ssh-keygen -t rsa -C "your_email@youremail.com"
```

- 输入cd指令，进入当前用户目录, cd ~

- 输入ls -a指令，查看当前用户目录下所有文件，包括隐藏文件

- 输入cd .ssh指令，进入.ssh目录

- 输入ls指令，查看.ssh目录下的文件

- 输入cat id_rsa.pub指令，查看id_rsa.pub文件中内容, 另外一个问价是私钥，不能泄漏

  

### [分支(branch)](https://blog.csdn.net/return_cc/article/details/78321038)

```
# 创建分支
git branch <branch_name>
# 切换分支
git checkout <branch_name>
## 以上两条命令可合并为 git checkout -b <branch_name>

# 快速切换到上一个分支
git checkout -

# 与远程分支关联 BowlingScore为仓库名
git remote add origin https://github.com/yangxiaoyan20/BowlingScore.git
# 上传分支
git push origin <branch_name>

# 合并分支，例如master分支是主要使用的，submain分支是另外一个用于测试master分支下文件可用性的分支，如果submain分支下的文件没有问题，现在想要把submain分支的修改内容与master中的文件合并
git checkout master
git merge submain

# 删除submain分支
git branch -d submain
```

### 不同 different

```
# 输出工作区，暂存区和本地最近版本(commit)的不同(different)
git diff HEAD
```

### 给 git 命令起别名(alias-别名)

``` 
# git config --global alias.<handle> <command>
git config --global alias.st status
```

### 

### 参考链接

[本地和远程仓库本质](https://www.cnblogs.com/snowdreams1006/p/10597579.html)

[Git本地仓库与GitHub远程仓库的同步方法](https://blog.csdn.net/lixiuxiu2017/article/details/79495884)

