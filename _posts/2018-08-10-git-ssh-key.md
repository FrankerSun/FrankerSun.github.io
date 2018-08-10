---
layout: post
title: "git ssh key"
category: 
excerpt: ""
tags: []
---

### 生成密钥
SSH公钥默认在 ~/.ssh ： fileName.pub 后缀的文件为公钥；对应的fileName文件为密钥。  
``` 
$ cd ~/.ssh && ls
id_rsa  id_rsa.pub  known_hosts
```

如果不存在，则需要生成  
```
$ ssh-keygen -t rsa -C "your_email@youremail.com"

Enter file in which to save the key (/path/to/your/.ssh/id_rsa):
如不需要修改文件名称，则直接按Enter。

Enter same passphrase again: [Type passphrase again]
提示输入密码：输入密码后push、pull只需输入此密码即可，也可选择不输入密码。
```

### 添加公钥到你的远程仓库（github）
1. 查看公钥：  
```
$ cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADSGHKAHLKJGFAHLJKGFAYGFIO$EGUGUIDYUIHASDDHKGFUHLGFVOIUYAGHJKLFADHKJLGFHKJLADGHJKLADSKJHLGAHKJLDGHJKLADGHJKLADHJKLGKJHLADGKJLHAHDJKGHKJLADGHJKAGE your_email@youremail.com
```
2. 登陆github/gitlab，找到SSH-KEY设置的地方  
3. 将公钥复制进去[全部复制]，并保存  
```
ssh-rsa AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAADSGHKAHLKJGFAHLJKGFAYGFIO$EGUGUIDYUIHASDDHKGFUHLGFVOIUYAGHJKLFADHKJLGFHKJLADGHJKLADSKJHLGAHKJLDGHJKLADGHJKLADHJKLGKJHLADGKJLHAHDJKGHKJLADGHJKAGE your_email@youremail.com
```

### 修改本地仓库的remote url
1. 查看 remote origin url   https开头表示HTTP协议;如果是SSH协议，则会是git开头  
```
$ git remote -v
origin https://github.com/account/project-name.git (fetch)
origin https://github.com/account/project-name.git (push)
```

2. 调整 remote origin url  
```
git remote set-url origin git@github.com:account/project-name.git
```