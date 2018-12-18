### 配置用户信息（例）：

git config --global user.name "John Doe"

git config --global user.email [johndoe@example.com](mailto:johndoe@example.com)

### 查看配置信息（例）：

git config --list

### 查看Git帮助命令：

git help <verb>

### 初始化仓库：

git init

### 对仓库文件追踪，提交（例）

git add *.c

git add README

git commit -m 'initial project version'

### 从远程仓库克隆（例）

git clone <git://github.com/schacon/grit.git>



### 切换,合并,查看分支

git branch 分支名        --创建分支

git checkout 分支名      --切换分支

git merge 分支名         --合并分支

git branch               -- 查看分支

git checkout -b 分支名   --创建并切换到一个分支





git init --bare     --初始化一个空的git仓库



git push origin master   --将远程库内容拉取到本地仓库

git remote add origin [git@github.com](mailto:git@github.com):michaelliao/learngit.git    --将本地仓库与远程仓库关联

git remote remove origin   -- 移除本地库与远程库的关联



相关资料:

[官方教程](<https://git-scm.com/book/zh/v1/%E8%B5%B7%E6%AD%A5-%E5%88%9D%E6%AC%A1%E8%BF%90%E8%A1%8C-Git-%E5%89%8D%E7%9A%84%E9%85%8D%E7%BD%AE>)

[阮一峰: git原理入门](http://www.ruanyifeng.com/blog/2018/10/git-internals.html)