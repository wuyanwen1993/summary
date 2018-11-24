# git  的常用操作

## 新建分支

git checkout master  # 切换到主分支

git checkout -b static-pages  # 创建并切换到 static-pages 新分支

## 合并、删除分支

git merge fake-branch  #合并分支

git branch -d fake-branch  # 删除分支





```
echo "# sample" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:wuyanwen1993/sample.git
git push -u origin master
```

```
git remote add origin git@github.com:wuyanwen1993/sample.git
git push -u origin master
```