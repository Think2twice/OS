# # 在mac下安装git的方法
## 一.首先安装homebrew（homebrew是什么具体可以上网搜，这里可以粗略地理解为Mac App Store）

::homebrew官网给的下载命令速度很慢，这里给出国内的镜像::

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
查看homebrew是否安装成功
`brew -v`
安装好homebrew 以后安装
`brew install git`
::在输入以上命令之前换一下源::
### 1.换源
```
// 替换brew.git
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

// 替换homebrew-core.git
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git
```
### 2.更新.bash_profile
```
// 如果home目录下没找到.bash_profile文件直接创建即可
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.bash_profile

source ~/.bash_profile
```
### 3.有的可能是zsh
```
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zsh_profile

source ~/.zsh_profile
```
查看安装是否成功
`git —version`
安装成功后便可以在GitHub上进行连接啦😀

## 二.注册GitHub的账号
创建repository（仓库）

## 三.在终端上与GitHub进行连接（第一次需要，以后初始化就可）基本信息设置
`git config -—global user.name  “你GitHub上的用户名”`
`git config —-global user.email “你GitHub登陆的邮箱”`
## 四.仓库中添加文件
### 1.在 ~工作区~ （working directory）添加文件
`cd Document`
`mkdir test`
`git init`
::`touch 文件名`::
`git status  //可以看到你还没有提交到暂存区，文件名是红色的`
### 2.将工作区中的文件放到 ~暂存区~ （staging area）
::`git add 你刚才创建的文件`::
`git status`
### 3.将文件从暂存区提交到 ~本地仓库~ 中（git repository）
::`git commit -m '你的描述whatever'`::
### 4.修改仓库文件
`vim 文件.txt`
在这一步会看到modified ‘你修改的文件’
`git add '文件.txt'`
`git status`
`git commit -m '通过git修改文件并提交到仓库`
### 5.删除仓库文件
```
rm -rf wenjian.txt
git rm wenjian.txt
git commit -m '删除文件'
```
## 五.Git管理远程仓库（协同工作）
`git clone “你clone下来的项目”`
再在你clone的项目下面来创建你要添加的内容，或者要对内容进行的修改
1.将本地仓库同步到git远程仓库中
```
git config --list
git remote -v
```
## 六.提交到远程仓库
`git push`




