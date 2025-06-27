
1. fork 原始项目

2. 从你的仓库拉取项目

3. 设置本地仓库的远程分支upstream

```shell
git remote add upstream https://github.com/XXXX/XXX.git
# 查看远程仓库设置
git remote -v
```

4. 更新远程仓库
```shell
git checkout main
git pull upstream main
git push origin main
```

5. 创建分支
```shell
git checkout -b fix/your-feature-or-fix-name
```

6. 修改完成提交
```shell
git add .
git commit -m "fix: XXX"
git push origin fix/your-feature-or-fix-name
```

7. 切回main 更新一下
```shell
git checkout main
git pull upstream main
git checkout fix/your-feature-or-fix-name
git rebase main
# 或者使用 merge，会创建一个合并提交
# git merge main
```