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

### 提交文件

```
# 文件已修改
git add <文件名> # 提交到暂存区
git status # 查看文件状态
git commit -m '备注修改的内容简介(可中文)'
git status
## 以上相当于对本地仓库操作(不会传到github中)
git push # 提交修改到远端仓库(提交到GitHub仓库中)
```

#### 其他文件操作

```
# 撤销 add
git reset .

# 删除文件
rm <文件名>
git rm <文件名>
git commit -m 'delete'
```



### 生成密钥

```
ssh-keygen -t rsa -C "your_email@youremail.com"
```

- 输入cd指令，进入当前用户目录

- 输入ls -a指令，查看当前用户目录下所有文件，包括隐藏文件

- 输入cd .ssh指令，进入.ssh目录

- 输入ls指令，查看.ssh目录下的文件

- 输入cat id_rsa.pub指令，查看id_rsa.pub文件中内容

  

### clone

```
git clone <仓库地址> <本地目录>
```

### [分支(branch)](https://blog.csdn.net/return_cc/article/details/78321038)

```
# 创建分支
git branch <branch_name>
# 切换分支
git checkout <branch_name>
## 以上两条命令可合并为 git checkout-b <branch_name>

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

