# 设置git全局邮箱和用户名
git config --global user.name "yourgithubname"
git config --global user.email "yourgithubemail"

# 查看分支
git branch

# 创建并设为默认分支
git checkout -b xxx

# 切换分支
git checkout xxx

# 删除本地分支
 git branch -d xxx

# 删除远程分支(在此之前确认该分支不为默认分支)
git push origin --delete xxx

# 设置ssh key
ssh-keygen -t rsa -C "youremail"

# 另一终端操作时
npm install hexo-deployer-git --save #安装hexo-deployer(node_modules文件夹)

# ----------日常----------

## 添加更改文件到缓存区
git add .

## 提交到本地仓库
git commit -m "更新说明"

## 推送到远程仓库进行备份
git push -u origin hexo