# 设置git全局邮箱和用户名
``` shell
git config --global user.name "yourgithubname"
git config --global user.email "yourgithubemail"
```

# 查看分支
``` shell
git branch
```

# 创建并设为默认分支
``` shell
git checkout -b xxx
```

# 切换分支
``` shell
git checkout xxx
```

# 删除本地分支
``` shell
git branch -d xxx
```

# 删除远程分支(在此之前确认该分支不为默认分支)
``` shell
git push origin --delete xxx
```

# 设置ssh key
``` shell
ssh-keygen -t rsa -C "youremail"
```

# 另一终端操作时,先安装hexo-deployer-git(会创建node_modules文件夹)
``` shell
npm install hexo-deployer-git --save
```

# 抓取远程仓库所有分支更新并合并到本地
``` shell
git pull
```

# 抓取远程仓库master分支merge到当前分支
``` shell
git pull origin master
```

# 合并远程和本地的库
``` shell
git pull --rebase origin master
```

# 抓取远程仓库更新
``` shell
git fetch origin
```

# push所有分支
``` shell
git push
```

# 将本地主分支推到远程主分支
``` shell
git push origin master
```

# 将本地主分支推到远程主分支(若无远程主分支则创建，用于初始化远程仓库)
``` shell
git push -u origin master
```

# 查看远程服务器地址和仓库名称
``` shell
git remote -v
```

# 添加远程仓库地址
``` shell
git remote add origin git@github.com:yourgitname/yourrepname.git
```

# 设置远程仓库地址
``` shell
git remote set-url origin git@github.com:yourgitname/yourrepname.git
```

# 删除远程仓库
``` shell
git remote rm xxx
```

# -----动漫人物-----

## 在项目中下载live2d模块
``` shell
npm install --save hexo-helper-live2d
```

## 下载相应的模型（xxx为模型名字）
``` shell
npm install live2d-widget-model-xxx
```

## 配置文件_config.yml引入模型
``` shell
live2d:
 enable: true
 scriptFrom: local
 model:
  use: live2d-widget-model-xxx
 display:
  position: right
  width: 150
  height: 300
 mobile:
  show: false
```

## 原作者预览
<https://huaji8.top/post/live2d-plugin-2.0/>

# --------------------日常--------------------

## 添加更改文件到缓存区
``` shell
git add .
```

## 提交到本地仓库
``` shell
git commit -m "更新说明"
```

## 推送到远程仓库进行备份
``` shell
git push -u origin hexo
```

## 注意
**从github上下载的主题或内容，提交前要删掉所下载文件中的.git相关文件，否则会push失败**