---
title: Centos安装jenkins
---

> yum的repo中默认没有Jenkins，需要先将Jenkins存储库添加到yum repos，执行下面的命令：
``` Shell
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo 
```

> 然后执行下面的命令：没搞清楚这是干啥用的
``` Shell
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

> 安装Jenkins
``` Shell
yum install -y jenkins
```

> 启动jenkins
``` Shell
service jenkins start
```