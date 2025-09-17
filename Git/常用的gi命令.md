```shell
# 撤回上一次提交，但保留代码
git reset --soft HEAD~1

# 撤回上一次提交和暂存（代码保留）
git reset --mixed HEAD~1
# 完全回滚到上一次提交前（代码也丢）

git reset --hard HEAD~1
# 临时保存
git stash          
# 查看保存列表
git stash list    
 # 恢复最新保存 
git stash apply   
# 删除某条 stash
git stash drop 
# 恢复并删除    
git stash pop      

```