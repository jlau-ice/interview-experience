
主分支            ---> dev
你牵出来开发的分支  ----> dev-xxx

你在 dev-xxx 开发完成后提交了

一般流程是 合并 dev-xxx 到 dev
这样会多一次合并的信息

可以这样

```shell
# 从主分支获取最新的代码
git checkout dev
git pull origin main 
```

```shell
# 切换到你开发功能的分支
git checkout dev-xxx
```

```shell
### 执行rebase 操作
git rebase dev
git checkout dev 
git merge dev-xxx
```
执行这个命令后，Git 会找到 dev-xxx 和 dev 分支的共同祖先。
然后，它会将 dev-xxx 分支上，那些在 dev 分支上没有的提交（也就是你在 dev-xxx 上做的开发提交）暂时“取下”。
接着，它会将 dev 分支前进到最新状态。
最后，Git 会将之前“取下”的 dev-xxx 分支上的提交，依次重新应用到 dev 分支的最新提交之上。这些重新应用的提交会有新的哈希值，因为它们的父提交变了。
如果在这个过程中发生冲突 (conflict)，Git 会暂停 rebase。你需要手动解决冲突，然后使用 git add . 将解决后的文件标记为已解决，最后运行 git rebase --continue 继续变基过程。如果想放弃变基，可以使用 git rebase --abort。
